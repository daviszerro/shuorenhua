# 说人话：中文 AI 腔检测与诊断工具

<p align="center">
  <strong>教 AI 如何识别用户指定的文本是否为 AI 生成。</strong>
</p>

`说人话` 专治那种“每个字都对，但一看就是模型生成的”中文 AI 腔。它不作为一个简单的同义词替换器，也不是无脑封杀所有技术词汇；它通过检测词汇特征、结构反模式、语用谄媚度以及句长均匀度，输出结构化的诊断报告，给出置信度评估，并利用排噪防误杀规则保护正常的技术事实和语域。

它适合这些场景的诊断：

| 场景 | 诊断侧重 |
|------|----------|
| 日常聊天 (`chat`) | 识别开场套话、谄媚元评论、虚假共情与身份认证式夸奖 |
| 技术状态同步 (`status`) | 识别空泛的自夸词、无事实指标的过度承诺，同时保护正常的时间、进度和动作 |
| 技术文档/注释 (`docs`) | 识别过度拟人化的虚假主语、被动堆砌、无源引用，保护代码/配置/命令等噪音 |
| 公开写作 (`public-writing`) | 全量扫描 Tier 1/2/3 词汇和 19 类结构反模式（二元对比、否定式列举、正能量总结强迫症等） |

---

## 诊断流程说明

`说人话` 诊断系统固定五步走：

1. **场景判定**：划分 `chat / status / docs / public-writing`，匹配相应的合理语域。
2. **划定排噪片段 (Protected Spans)**：识别数字、版本、命令、路径、报错、引用原文、人名和系统主语。这些段落在检测时将自动放行，不计入 AI 腔得分。
3. **特征扫描**：
   - **词汇特征**：匹配 Tier 1 (高频 AI 词)、Tier 2 (段落聚集词) 和 Tier 3 (高饱和词)。
   - **结构特征**：匹配 19 种结构反模式（如“二元对比假戏剧”、“否定式列举”、“戏剧化碎句”）。
   - **翻译腔特征**：匹配长定语链、被动堆砌等由英文直译而来的中文痕迹。
4. **免误杀校准**：对照排噪和案例规范，对命中的词汇在特定场景下的合理性进行校准。
5. **置信度评分**：根据命中的严重度和聚集度评估整体 AI 置信度（高/中/低），输出包含详细证据链的结构化报告。

---

## 30 秒上手

### Claude Code

将 skill 放入 skills 目录，之后在对话中说“诊断这段话的 AI 味”：

```bash
git clone https://github.com/MrGeDiao/shuorenhua.git
mkdir -p ~/.claude/skills
cp -r shuorenhua ~/.claude/skills/shuorenhua
```

装好后，对 Claude 说「读取 ./SKILL.md，按其中规则诊断以下文本：……」即可。

### ChatGPT / Custom GPT

直接将 `SKILL.md` 和 `references/` 文件夹中的规则作为 Custom GPT 的 Instructions 和 Knowledge 知识库上传。

---

## 评测数据集

规则层覆盖 210+ 中文短语、96 条英文短语、19 类结构反模式。

评测集共 75 条：
- **Should Fix (SF) 案例 (42条)**：应当被成功检出为 AI 生成（中/高置信度），并指出特征。
- **Should NOT Fix (SNF) 案例 (33条)**：应当被安全放行判定为人类撰写（低置信度），并通过排噪规则排除字面误判。

---

## 目录结构说明

- [SKILL.md](./SKILL.md)：核心检测诊断 Prompt 规范。
- [references/](./references/)：诊断特征库：
  - [phrases-zh.md](./references/phrases-zh.md)：中文 AI 腔高频特征词。
  - [phrases-en.md](./references/phrases-en.md)：英文 AI 腔高频特征词。
  - [structures.md](./references/structures.md)：19 种结构反模式。
  - [severity.md](./references/severity.md)：检测严重度与置信度计算规则。
  - [protected-spans.md](./references/protected-spans.md)：检测排噪规范（哪些内容不判定为 AI 腔）。
  - [boundary-cases.md](./references/boundary-cases.md)：检测防误杀参考实例。
- [evals/](./evals/)：评测集与评测指南。
