# Benchmark Eval Harness — 运行说明

> v2.0.0 起使用的 AI 腔检测诊断模型实跑入口。
> Prompt 本体见 `./detect-prompt.md` 和 `./judge-prompt.md`。

## 文件约定

工具本体（committed）：

| 角色 | 路径 |
|------|------|
| 被测模型诊断 prompt | `automation/eval/detect-prompt.md` |
| 交叉判分 prompt | `automation/eval/judge-prompt.md` |
| 运行说明 | `automation/eval/README.md`（本文件） |

运行实例（local-only，`tasks/` 在 `.gitignore` 内）：

| 角色 | 路径 |
|------|------|
| Codex 诊断输出 | `tasks/current/eval-runs/<YYYY-MM-DD>-codex/detect-<batch>.md` |
| Claude 诊断输出 | `tasks/current/eval-runs/<YYYY-MM-DD>-claude/detect-<batch>.md` |
| Claude 判 Codex | `tasks/current/eval-runs/<YYYY-MM-DD>-judge/claude-judge-codex-<batch>.md` |
| Codex 判 Claude | `tasks/current/eval-runs/<YYYY-MM-DD>-judge/codex-judge-claude-<batch>.md` |

第一次使用前先建目录：

```bash
mkdir -p tasks/current/eval-runs/2026-07-05-codex \
  tasks/current/eval-runs/2026-07-05-claude \
  tasks/current/eval-runs/2026-07-05-judge
```

## 批次划分

默认按 5 批跑：

| batch | 区间 |
|-------|------|
| `SF01-14` | SF-01 到 SF-14 |
| `SF15-28` | SF-15 到 SF-28 |
| `SF29-42` | SF-29 到 SF-42 |
| `SNF01-16` | SNF-01 到 SNF-16 |
| `SNF17-33` | SNF-17 到 SNF-33 |

## 诊断批

Codex 诊断一批：

```bash
codex exec -C . -s read-only --ephemeral \
  -o tasks/current/eval-runs/2026-07-05-codex/detect-SF01-14.md \
  '你正在执行说人话 AI 腔检测 benchmark 诊断实跑。

请完整读取 ./automation/eval/detect-prompt.md，按其中 text 代码块里的 prompt 行事。
只使用当前工作目录下的 ./SKILL.md、./references/ 和 ./evals/。

本轮只处理 ./evals/benchmark.md 中 SF-01 到 SF-14。
请直接输出最终结果，不要附加过程叙述。'
```

Claude 诊断一批：

```bash
claude --print --model opus \
  --name shuorenhua-eval-detect-SF01-14 \
  --disallowedTools Edit Write \
  > tasks/current/eval-runs/2026-07-05-claude/detect-SF01-14.md <<'EOF'
你正在执行说人话 AI 腔检测 benchmark 诊断实跑。

请完整读取 ./automation/eval/detect-prompt.md，按其中 text 代码块里的 prompt 行事。
只使用当前工作目录下的 ./SKILL.md、./references/ 和 ./evals/。

本轮只处理 ./evals/benchmark.md 中 SF-01 到 SF-14。
请直接输出最终结果，不要附加过程叙述。
EOF
```

## 判分批

Claude 判 Codex 诊断报告：

```bash
claude --print --model opus \
  --name shuorenhua-eval-judge-codex-SF01-14 \
  --disallowedTools Edit Write \
  > tasks/current/eval-runs/2026-07-05-judge/claude-judge-codex-SF01-14.md <<'EOF'
你正在执行说人话 AI 腔检测 benchmark 交叉判分。

请完整读取 ./automation/eval/judge-prompt.md，按其中 text 代码块里的 prompt 行事。
只使用当前工作目录下的 ./evals/、./SKILL.md、./references/ 和被测输出文件。

benchmark 区间：SF-01 到 SF-14
被测输出：./tasks/current/eval-runs/2026-07-05-codex/detect-SF01-14.md

请直接输出判分表和汇总，不要重写被测输出。
EOF
```
