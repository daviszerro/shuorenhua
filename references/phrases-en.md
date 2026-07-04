# 英文 AI 腔特征词汇库 (English AI-Tone Phrases Ledger)

> 英文 AI 腔高频词汇分类，用于 AI 腔诊断匹配。

## Tier 1：默认匹配特征 (高置信度指标)

以下词汇/短语在 AI 生成的英文文本中出现频率极高，默认判定为 AI 腔。

### 1.1 开场套话与元评论 (Throat-clearing openers & Meta)
- `Here's the thing`
- `The uncomfortable truth is`
- `Can we talk about`
- `Let's be honest`
- `I'll be frank`
- `It's worth noting that`
- `At its core`
- `At the end of the day`
- `In today's world`
- `In a world where`
- `What this means is`
- `It's important to note`
- `In this essay we will explore`
- `As we'll see`
- `Here is a/an`

### 1.2 情绪与谄媚垫片 (Sycophantic / Emphasis crutches)
- `Full stop.`
- `Let that sink in.`
- `Make no mistake.`
- `Mark my words.`
- `I promise.`
- `Read that again.`
- `Period.`
- `Great question!`
- `You're absolutely right!`
- `Certainly!`
- `Of course!`
- `I hope this helps!`
- `Let me know if you'd like me to expand`

### 1.3 商业/互联网黑话 (Business jargon)
- `leverage`
- `navigate`
- `unpack`
- `lean into`
- `deep dive`
- `game-changer`
- `circle back`
- `synergy`
- `ecosystem`
- `streamline`
- `empower`
- `actionable`
- `learnings`
- `thought leader`
- `best practices`
- `holistic`

*(注：在图、网络、路由或路径搜索等字面技术语境中放行，如 `navigates the network topology`)*

### 1.4 虚假修饰词与夸张动词 (Inflated verbs & Significance inflation)
- `utilize`
- `commence`
- `endeavor`
- `ascertain`
- `facilitate`
- `cultivate`
- `elucidate`
- `ameliorate`
- `galvanize`
- `bolster`
- `spearhead`
- `catalyze`
- `reimagine`
- `testament to`
- `serves as`
- `stands as`
- `showcases`
- `underscores`
- `highlights`
- `pivotal`
- `groundbreaking`
- `cutting-edge`
- `watershed moment`
- `indelible mark`
- `paradigm shift`

### 1.5 连系动词滥用与冗长填充 (Copula avoidance & Filler)
- `serves as a`
- `stands as a`
- `represents a`
- `functions as a`
- `boasts a`
- `features a`
- `presents a`
- `In order to`
- `Due to the fact that`
- `At this point in time`
- `It is important to note that`
- `The system has the ability to`
- `It goes without saying`

---

## Tier 2：同段聚集特征 (中置信度指标)

以下词汇单独使用时正常，但在同一段落内密集聚集（2 个或更多）时，是 AI 腔的特征信号。

- `harness`
- `navigate`
- `foster`
- `elevate`
- `unleash`
- `resonate`
- `revolutionize`
- `underpin`
- `nuanced`
- `crucial`
- `multifaceted`
- `myriad`
- `plethora`
- `encompass`
- `transformative`
- `cornerstone`
- `paramount`
- `poised`
- `burgeoning`
- `nascent`
- `quintessential`
- `overarching`

---

## Tier 3：高频饱和特征 (低置信度指标)

普通词汇，只在全文中出现频率极高、密度过载时才作为 AI 腔的判定依据（阈值见 `severity.md`）。

- `significant`
- `innovative`
- `effective`
- `dynamic`
- `scalable`
- `compelling`
- `unprecedented`
- `exceptional`
- `remarkable`
- `sophisticated`
- `instrumental`
- `comprehensive`
- `robust`
- `seamless`

---

## 副词滥用特征 (Filler Adverbs)
AI 倾向于过度使用副词来增强确定性或渲染语气，若高频出现，可作为 AI 腔特征之一：
- `really`
- `just`
- `literally`
- `genuinely`
- `honestly`
- `deeply`
- `truly`
- `fundamentally`
- `essentially`
- `incredibly`
- `remarkably`
- `significantly`
- `interestingly`
- `importantly`
- `notably`
- `ultimately`
- `arguably`
- `undeniably`
