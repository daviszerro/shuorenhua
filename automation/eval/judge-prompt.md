# Benchmark Judge Prompt

把下面这段 prompt 直接用于交叉判分。它只负责按 `evals/run-eval.md` 判定被测模型输出的诊断报告，不负责重新诊断。

```text
你正在执行「说人话：AI 腔识别与检测」benchmark 交叉判分。你的任务是读取 benchmark 用例、被测模型生成的诊断报告，并按照 ./evals/run-eval.md 的既有口径判定每条结果。

路径边界：
- 只使用当前工作目录里的 `./evals/`、`./SKILL.md`、`./references/` 和被测输出文件。
- 不要读取或引用全局安装副本，本轮判分口径以当前工作目录文件为准。

开始前先读取：
- ./evals/run-eval.md
- ./evals/benchmark.md

必要时再读取：
- ./SKILL.md
- ./references/protected-spans.md
- ./references/boundary-cases.md
- ./references/severity.md

输入会提供：
- benchmark 区间
- 对应 benchmark 诊断预期（见 ./evals/benchmark.md 中的 **预期**）
- 被测模型诊断报告

判分标准：
- 直接引用 ./evals/run-eval.md 的判定口径，不另造标准。
- SF 案例：如果正确诊断为 AI 生成 (高/中置信度) 并指出了预期的特征和词汇，判定为 ✅；若置信度或特征匹配不完整判定为 ⚠️；若诊断为人类撰写 (漏诊) 或严重误判判定为 ❌。
- SNF 案例：若正确判定为人类撰写 (低置信度 / 安全放行) 且进行了正确的排噪说明，判定为 ✅；若误诊为 AI 生成 (误杀) 判定为 ❌。

输出格式必须严格如下：

| 编号 | 判定 ✅/⚠️/❌ | 一句依据 |
|------|--------------|----------|
| SF-01 | ✅ | <匹配到了开场套话和谄媚词，符合预期> |

末尾再输出：

## 汇总

- SF 应检率：X/Y
- SNF 误检率：X/Y
- ⚠️ 清单：<编号列表；没有就写“无”>
- ❌ 清单：<编号列表；没有就写“无”>

禁止：
- 不要输出判定等级以外的新等级。
- 不要跳过用例。
```
