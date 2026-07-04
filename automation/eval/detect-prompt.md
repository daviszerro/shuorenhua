# Benchmark AI-Tone Detection Prompt

把下面这段 prompt 直接用于被测模型的诊断实跑。

```text
你正在执行「说人话：AI 腔识别与检测」benchmark 诊断实跑。你的任务是作为被测模型，读取当前仓库规则和指定的用例，对用例进行 AI 腔诊断，并输出标准的结构化诊断报告。

路径边界：
- 只使用当前工作目录里的 `./SKILL.md`、`./references/`、`./evals/` 和 `./automation/eval/`。
- 不要读取或引用全局安装副本，本轮实跑口径以当前工作目录文件为准。

开始前先读取：
- ./SKILL.md
- ./evals/benchmark.md
- ./evals/run-eval.md

再读取相关的特征与排噪规则：
- ./references/phrases-zh.md
- ./references/phrases-en.md
- ./references/structures.md
- ./references/severity.md
- ./references/protected-spans.md
- ./references/boundary-cases.md

输入会指定一个 benchmark 区间，例如：
- SF-01 到 SF-14
- SF-15 到 SF-28
- SF-29 到 SF-42
- SNF-01 到 SNF-16
- SNF-17 到 SNF-33

每条用例的字段以 ./evals/benchmark.md 为准，测试文本为引用块或代码块中的文字。

处理要求：
1. 逐条处理指定区间内的所有用例，不要跳过或合并用例。
2. 严格按照 ./SKILL.md 中定义的 Output contract 输出格式，为每一条用例输出包含 `## <用例编号>` 的结构化诊断报告。

输出格式示例：

## <用例编号>

# AI腔诊断报告

- **总体结论**：[AI 生成 (高置信度) / AI 生成 (中置信度) / 人类撰写 (低置信度 / 安全放行)]
- **文本场景**：[chat / status / docs / public-writing]

## 命中的 AI 腔特征

### 1. 词汇与短语特征 (Vocabulary Hits)
- **[Tier 1 默认特征]** 词汇: `...` | 证据句: "..." | 诊断理由: ...
...

### 2. 结构与段落特征 (Structural Hits)
- **[反模式名称]** 证据句: "..." | 诊断理由: ...
...

### 3. 语气与语用特征 (Pragmatic Hits)
- **[分析特征]** 证据句: "..." | 诊断理由: ...
...

## 免误杀与排噪分析 (Noise & False Positive Safeguards)
- 证据: "..." | 说明: ...

## 详细诊断推理过程 (Analysis Details)
...

---

禁止：
- 不要输出多余的客套话或前言，直接输出格式化结果。
- 每一条必须包含上述所有诊断小节（若无则填“无”）。
```
