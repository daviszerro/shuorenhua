# 结构反模式特征库 (Structural Anti-Patterns Ledger)

> 结构反模式是指在句子和段落层面上表现出来的 AI 生成特征。在诊断中，匹配这些结构模式是判定“高置信度 AI 生成”的重要依据。

---

## 1. 二元对比假戏剧 (False Dichotomy Drama)
- **特征模式**：先否定 X，再肯定 Y，试图人为制造戏剧效果或顿悟感。
- **AI腔表现**：
  > ❌ 这不是技术问题，而是管理问题。
  > ❌ It's not about the code. It's about the culture.
- **人类正常表现**（通常直接陈述逻辑或侧重关系）：
  > ✅ 管理流程比代码本身更容易出问题。
  > ✅ The culture around code review matters more than the code itself.

## 2. 否定式列举 (Negation Listing)
- **特征模式**：排比列举一堆“不是什么”，最后才引出“是什么”，行文冗长且戏剧化。
- **AI腔表现**：
  > ❌ 它不是框架，不是库，也不是工具——它是一种思维方式。
  > ❌ It's not a framework. It's not a library. It's a way of thinking.
- **人类正常表现**（直奔主题）：
  > ✅ 把它当作一种思维方式，不是一个具体工具。
  > ✅ Think of it as a mental model, not a tool.

## 3. 戏剧化碎句 (Dramatic Fragments)
- **特征模式**：通过单字、数字组成的句子碎片强行制造叙事悬念和历史厚重感。
- **AI腔表现**：
  > ❌ 三年。两个人。一个想法。
  > ❌ Three years. Two people. One idea.
- **人类正常表现**（正常记叙句）：
  > ✅ 两个人花了三年把这个想法做成了产品。
  > ✅ Two people spent three years turning the idea into a product.

## 4. 反问式铺垫 (Rhetorical Hooking)
- **特征模式**：在开头使用反问句或假设，故作神秘，试图调动读者情绪（“如果我告诉你……”）。
- **AI腔表现**：
  > ❌ 如果我告诉你，90% 的创业公司都在犯同一个错误呢？
  > ❌ What if I told you 90% of startups make the same mistake?
- **人类正常表现**（直接抛出事实与观点）：
  > ✅ 90% 的创业公司在定价上犯同一个错误：按成本定价而不是按价值定价。
  > ✅ 90% of startups misprice their product, using cost-based pricing instead of value-based.

## 5. 虚假主语 (False Agency)
- **特征模式**：将非人类、无生命的事物（如产品、工具、概念）赋予拟人化的动词（如“引领”、“驱动”、“助力”、“赋能”），且整个句子空洞无内容。
- **AI腔表现**：
  > ❌ 该框架赋能了开发者社区。
  > ❌ The framework empowers the developer community.
- **人类正常表现**（主语为人类，动作具体）：
  > ✅ 开发者用这个框架能少写 30% 的样板代码。
  > ✅ Developers write 30% less boilerplate with this framework.
  > *(注：技术文档中正常的系统行为描述如“网关在超时后返回 504”是合理的，不算虚假主语。)*

## 6. 被动语态堆砌 (Passive Voice Abuse)
- **特征模式**：连续使用被动语态（“被优化”、“被改进”），模糊动作执行者。
- **AI腔表现**：
  > ❌ 系统被全面优化后，性能被显著提升，用户体验被大幅改善。
  > ❌ The system was optimized, performance was improved, and user experience was enhanced.
- **人类正常表现**（以人或系统动作作为主动发起者，并带有具体结果）：
  > ✅ 我们优化了数据库查询，页面加载从 3 秒降到 0.8 秒。
  > ✅ We optimized database queries and cut page load time from 3s to 0.8s.
  > *(注：学术论文的常规客观被动，如“The experiment was conducted by...”，可合理放行。)*

## 7. 三件套排比列举 (Rule of Three Inflation)
- **特征模式**：AI 极度偏爱使用三个同类形容词或抽象名词进行排列，用以装饰句式。
- **AI腔表现**：
  > ❌ 创新、协作、卓越。
  > ❌ Innovation, collaboration, and excellence.
- **人类正常表现**（直陈动作，通常为一个或两个）：
  > ✅ 把东西做出来，做好。
  > ✅ Build things. Build them well.

## 8. “首先…其次…最后…”机械排列 (Mechanical Transitions)
- **特征模式**：硬套过渡结构，制造生硬且流于表面的条理感。
- **AI腔表现**：
  > ❌ 首先，我们需要明确目标；其次，制定计划；最后，执行落地。
- **人类正常表现**（自然的连贯步骤）：
  > ✅ 先把目标定清楚，然后排优先级，边做边调。

## 9. Wh- 引导词句式过度集中 (Wh- Cleft Sentences)
- **特征模式**：英文中过度集中使用以 What/When/Why 开头的强调句。
- **AI腔表现**：
  > ❌ What makes this approach unique is its simplicity.
- **人类正常表现**（使用直接的陈述句）：
  > ✅ This approach works because it's simple.

## 10. 空泛的总结式收尾 (Empty Concluding Signposts)
- **特征模式**：每段结尾或全文末尾强制使用“总之”、“综上所述”等总结句，实质内容只是前文的空洞重复。
- **AI腔表现**：
  > ❌ 综上所述，该方案在性能、安全性和可维护性方面都表现优异。
  > ❌ In conclusion, this approach excels in performance, security, and maintainability.
- **人类正常表现**：前面说完了就自然结束，不进行无信息增量的总结。

## 11. 对称填充 (Symmetry Padding)
- **特征模式**：为了追求句式对仗、四字成语平衡，硬凑毫无事实含义的偶数句。
- **AI腔表现**：
  > ❌ 既要保证速度，又要保证质量；既要创新突破，又要稳定可靠。
- **人类正常表现**（直接指出取舍或侧重点）：
  > ✅ 速度和质量之间我们优先质量。

## 12. 无源引用 (Unsourced Authority Claims)
- **特征模式**：使用“研究表明”、“数据显示”、“专家指出”来支撑论点，但无法给出具体时间、机构或研究背景，从而制造虚假的权威感。
- **AI腔表现**：
  > ❌ 研究表明，远程办公能提高 30% 的生产力。
  > ❌ Studies show that remote work increases productivity by 30%.
- **人类正常表现**（给出真实的归属和背景）：
  > ✅ Stanford 2023 年的一项实验发现，全远程员工的代码提交量比混合办公多 13%。
  > ✅ A 2023 Stanford experiment found fully remote employees committed 13% more code than hybrid workers.

## 13. 滥用加粗排版 (Mechanical Boldface)
- **特征模式**：机械化地在每一条列点的最前面使用加粗词汇（“**维度：**”、“**优化：**”），行文极度刻板。
- **AI腔表现**：
  > ❌ **用户体验：** 界面全面升级。**性能优化：** 算法显著提升。**安全加固：** 新增端到端加密。
- **人类正常表现**（自然的流水线文本或仅加粗真正关键的信息）：
  > ✅ 界面重新设计了，算法快了 2 倍，加了端到端加密。

## 14. 分条列点强迫症 (Obsessive Bullet-pointing)
- **特征模式**：哪怕是极短、极简单的对话，也要列出 1. 2. 3. 或项目符号，缺乏日常口语的连贯交流感。
- **AI腔表现**：
  > ❌ 关于这个问题，我的建议如下：
  >    1. 先检查配置文件
  >    2. 确认环境变量
  >    3. 重启服务
- **人类正常表现**（流畅简短的一两句话）：
  > ✅ 配置文件里的 DB_HOST 可能写错了，先看一眼。不是的话重启一下服务试试。

## 15. 正能量收尾强迫症 (Canned Uplifting Vibe)
- **特征模式**：无论文本本身是日常吐槽、技术复盘还是简单的更新，最后一段必须“上价值”、“展望未来”、“共同见证无限可能”。
- **AI腔表现**：
  > ❌ ……总之，让我们拥抱变化，积极迎接 AI 时代的无限可能！未来可期！
- **人类正常表现**：事实说完直接结尾，不做无病呻吟的煽情。

## 16. 假网感 / 硬凹流行语 (Fake Colloquialism)
- **特征模式**：AI 在试图接地气时，过度、批量的使用网络用语（“绝绝子”、“谁懂啊”、“狠狠心动”），反而显得僵硬。
- **AI腔表现**：
  > ❌ 姐妹们！这个工具真的绝绝子！谁懂啊，效率直接拉满！狠狠心动了！
- **人类正常表现**（自然的网感或平实的表达）：
  > ✅ 这个工具确实好用，主要是批量处理的速度快，省了不少时间。

## 17. 虚假的工程师调试叙事 (Pseudo-Engineering Narrative)
- **特征模式**：将专业的 SRE/排查词汇（“稳稳兜住”、“落盘”、“收口”、“对上”）滥用到完全不相关的日常或产品介绍中，制造虚假的“专业姿态”。
- **AI腔表现**：
  > ❌ 我已经把差异收窄了，根因基本坐实，接下来做一个更硬的排除法把问题打掉。
- **人类正常表现**（说人话）：
  > ✅ 原因找到了：是缓存过期导致的。我把可能性排查了一遍，现在就剩这一个。

## 18. 句长过于均匀 (Sentence Length Uniformity)
- **统计特征**：AI 生成的句子长度非常规整，标准差极低（句长标准差一般在 1.2 左右，而人类写作因长短句结合，标准差通常大于 4.7）。
- **诊断依据**：读起来缺乏“呼吸感”，整段句子字数和结构对称度极高。

## 19. 价值拔高骨架 (Inflationary Scaffolding)
- **特征模式**：用“不仅是……更是……”、“真正的……不是……而是……”强行把普通的事实拔高为具有哲学意义的“深度洞见”。
- **AI腔表现**：
  > ❌ 这不仅仅是一个产品，更是一种信念的传承。
  > ❌ 真正的竞争力不是功能堆砌，而是体验细节。最后比拼的是执行效率。
- **人类正常表现**（客观的评价与论述）：
  > ✅ 产品做得再多，最后还是看体验细节和执行效率。
