# Boris Cherny — Claude Code 创始人公开发言整理

> **Boris Cherny** 是 Anthropic Claude Code 的创始人兼负责人（Creator & Head of Claude Code）。
> 
> 本文档整理了他在 Twitter/X、播客、采访中的公开发言，按主题分类。持续更新。
>
> 来源：[@bcherny](https://x.com/bcherny) · [Lenny's Podcast](https://www.lennysnewsletter.com/p/head-of-claude-code-what-happens) · VentureBeat · Business Insider · PCMag

---

## 目录

- [人物背景](#人物背景)
- [Claude Code 的诞生故事](#claude-code-的诞生故事)
- [产品哲学](#产品哲学)
- [对软件工程未来的判断](#对软件工程未来的判断)
- [工作流与技术实践](#工作流与技术实践)
- [团队管理与组织设计](#团队管理与组织设计)
- [技术决策与产品细节](#技术决策与产品细节)
- [关键原则（分享给每位新成员）](#关键原则分享给每位新成员)
- [主要素材来源](#主要素材来源)

---

## 人物背景

- TypeScript 编程语言《Programming TypeScript》作者（O'Reilly 出版）
- 曾短暂离开 Anthropic 加入 Cursor，**两周后回归**（原因：在 Anthropic 还有未竟之事）
- 目前同时负责 Claude Code 和 Cowork（Anthropic 面向企业的 AI 协作产品）
- X 主页：[@bcherny](https://x.com/bcherny) | 个人网站：[borischerny.com](https://borischerny.com)

---

## Claude Code 的诞生故事

### 从一个"意外"开始

> "It was an accident that changed everything."
> — PCMag 采访标题

Claude Code 最初只是一个**简单的终端原型（terminal-based prototype）**，不是经过精心规划的大项目，而是一个快速 hack 演变而来的工具。

- 启动时间：大约一年前（~2025年初）
- 现状（2026年初）：**占据 GitHub 公开 commit 的 4%**，DAU 上个月翻倍
- 收入：**$1 billion ARR**（年化营收 10 亿美元），是 Anthropic 发展最快的产品之一

### 短暂离开 Cursor 的插曲

Boris 曾离开 Anthropic 去 Cursor，但**仅两周就返回**。这件事本身说明他对 Claude Code 还有强烈的未竟心愿——Lenny's Podcast 中专门提及此事，显示他对这个产品的执念不是表演性的。

---

## 产品哲学

### 1. 满足"潜在需求"，而非用户说出口的需求（Latent Demand）

Lenny's Podcast 中 Boris 明确讲了这一反直觉原则：Claude Code 的成功来自于**挖掘用户没有明确表达、但真实存在的需求**，而不是照着用户反馈单做。

> 这与经典产品思维一致：用户说"我要更快的马"，但真正的需求是"更快地到达目的地"。

### 2. 反直觉的产品原则（Counterintuitive Product Principles）

Lenny 播客中反复提到，Claude Code 的成功路径有几条反直觉原则：

- **刻意"欠配置"团队**（underfunding teams）：团队规模保持小，逼出创造力
- **给团队无限 token 额度**：工程师自己是 Claude Code 的重度用户，只有用得多才能真正理解产品
- **不依赖大规模组织扩张**：Anthropic 证明，用更好的模型编排可以获得指数级生产力，而非靠堆人头

### 3. 验证循环是核心（Verification Loop）

> "Probably the most important thing to get great results out of Claude Code — give Claude a way to verify its work. If Claude has that feedback loop, it will 2-3x the quality of the final result."
> — @bcherny，X thread，2026年1月

Claude Code 不只是生成代码，它要能**自己验证代码是否工作**：
- 打开浏览器测试 UI
- 运行 bash 命令
- 跑测试套件
- 用 Claude Chrome 扩展做端到端测试

### 4. 每个错误都是一条规则（Every Mistake Becomes a Rule）

团队维护一个 `CLAUDE.md` 文件放在 git repo 里：

> "Anytime we see Claude do something incorrectly we add it to the CLAUDE.md, so Claude knows not to do it next time."
> — @bcherny

在 code review 时，工程师会 tag `@claude` 让它自己把规则写进 CLAUDE.md。Boris 称之为 **"Compounding Engineering"**（复利工程），借鉴自 Dan Shipper 的概念——团队合作越久，AI 越智能。

---

## 对软件工程未来的判断

### "编程已经被解决了"（Coding is Solved）

这是 Boris 最具争议也最被广泛引用的判断：

> Boris believes coding is "solved" — the bottleneck in software development has shifted from writing code to higher-order thinking.

他的意思不是"不需要程序员了"，而是：
- **写代码本身不再是瓶颈**
- 软件工程师的角色将演变——从"写代码的人"变成"指挥 AI 舰队的人"
- Business Insider 采访中他说：**"software engineer" 这个职位名称可能会消失**，取而代之的是新的角色定义

### 工程师角色的演变

> "The tools to multiply human output by a factor of five are already here. They require only a willingness to stop thinking of AI as an assistant and start treating it as a workforce."
> — VentureBeat 引用

他描述了新的工作方式：
- 不再是"内循环"（写一个函数→测试→写下一个）
- 而是像**星际争霸（Starcraft）**——你是战略指挥官，管理多支 AI 并行部队
- 一个人 = 一个小型工程部门的产出

### 关于 AI 替代的清醒

虽然他说"coding is solved"，但他并非技术乐观主义的无脑鼓吹者：
- Spotify 案例（2026年2月）：Spotify 最好的开发者自 2025年12月起没写过一行代码
- 他承认这个转型对工程师群体是真实的冲击，不是"被淘汰"，而是"角色重新定义"

---

## 工作流与技术实践

> 来源：@bcherny 的两条 X thread（2026年1月2日 & 1月31日），已成为开发者社区热议话题

### 并行代理工作流（Fleet Commander Mode）

**Boris 的终端设置：**
- 同时跑 **5 个 Claude Code 实例**，分 5 个 tab（编号 1-5）
- 每个 tab 是同一 repo 的独立 git checkout，避免冲突
- 用 iTerm2 系统通知知道哪个 Claude 需要输入
- 浏览器同时跑 **5-10 个 claude.ai/code** session
- 早上在手机 Claude iOS app 启动任务，到电脑上接力

**他的比喻：**
> "feels more like Starcraft than traditional coding"

### 模型选择：永远用最慢最强的（Opus 4.5 + Thinking）

> "I use Opus 4.5 with thinking for everything. It's the best coding model I've ever used, and even though it's bigger & slower than Sonnet, since you have to steer it less and it's better at tool use, it is almost always faster than using a smaller model in the end."
> — @bcherny

**关键洞察：** 瓶颈不是 token 生成速度，是人花在纠正 AI 错误上的时间。用更聪明的模型，前期"算力税"换来后期"纠错税"的消除。

### CLAUDE.md：团队共享的 AI 记忆

```markdown
**Always use `bun`, not `npm`.**

bun run typecheck
bun run test -- -t "test name"
bun run lint:file -- "file1.ts"
bun run lint && bun run test
```

整个团队每周多次贡献内容，code review 时顺手让 Claude 自己更新：

```
nit: use a string literal, not ts enum

@claude add to CLAUDE.md to never use enums,
always prefer literal unions
```

### Plan Mode 工作流

1. 用 `shift+tab` 双击进入 Plan Mode
2. 和 Claude 反复打磨计划直到满意
3. 切换到 auto-accept 模式
4. Claude 一次性实现

> "A good plan is really important to avoid issues down the line."

**团队变体：** 一个人用 Claude A 写计划，再用 Claude B 以 staff engineer 角色审计划。

### Slash Commands（斜杠命令）

最常用的命令之一：

```
/commit-push-pr
```

一键完成：commit → push → 开 PR。命令存放于 `.claude/commands/`，团队共享。

斜杠命令可以内嵌 bash（如预先 `git status`），减少额外的模型调用。

### 子代理（Subagents）

```
.claude/agents/
  build-validator.md
  code-architect.md
  code-simplifier.md   ← 代码完成后清理架构
  oncall-guide.md
  verify-app.md        ← 端到端测试指南
```

相当于把最常见的 PR 工作流自动化。

### PostToolUse Hook：自动格式化

```json
"PostToolUse": [
  {
    "matcher": "Write|Edit",
    "hooks": [
      {
        "type": "command",
        "command": "bun run format || true"
      }
    ]
  }
]
```

Claude 90% 时候代码格式没问题，hook 处理边缘情况，避免 CI 失败。

### 权限管理

不用 `--dangerously-skip-permissions`，用 `/permissions` 预先允许常见安全命令，存在 `.claude/settings.json`：

```
Bash(bun run build:*)
Bash(bun run test:*)
Bash(bun run lint:file:*)
Bash(find:*)
...
```

### 工具集成（MCP）

Claude Code 直接调用：
- **Slack MCP server**（搜索、发帖）
- **BigQuery** via `bq` CLI（跑数据查询）
- **Sentry**（抓错误日志）

```json
{
  "mcpServers": {
    "slack": {
      "type": "http",
      "url": "https://slack.mcp.anthropic.com/mcp"
    }
  }
}
```

### RAG 的取舍

> "We did RAG early on then unshipped it for a number of reasons: privacy, security, reliability, index staleness. Overall, we found that agentic search gave better results with fewer tradeoffs."
> — @bcherny，X，2026年2月

如果用户偏好 RAG，他推荐用 Sourcegraph MCP，或直接让 Claude 自己建代码索引。

### Auto Mode（2026年3月新功能）

> "New in Claude Code: auto mode. Instead of approving every file write and bash command, or skipping permissions entirely, auto mode lets Claude make permission decisions on your behalf. Safeguards check each action before it runs."
> — @bcherny，X，2026年3月

---

## 团队管理与组织设计

### "故意欠配置"策略（Intentional Underfunding）

Lenny's Podcast 中：Claude Code 团队**刻意保持小规模**。这不是资源不足，而是有意为之：
- 小团队被迫更创造性地使用 AI 工具
- 工程师既是产品的构建者，也是最重度的使用者
- 给团队**无限 token 额度**——让他们充分体验自己做的产品

这与 Anthropic 总裁 Daniela Amodei 的"Do more with less"战略一致。

### 团队文化：像用户一样使用自己的产品

Boris 的整个工作流本身就是一个活广告——他的工作方式直接影响了 Claude Code 的产品决策。Claude Code 团队是自己产品的最重度用户。

---

## 技术决策与产品细节

### 为什么选 Terminal-first，而非 IDE 插件？

Claude Code 从一开始就是终端工具，不是 IDE 插件（对比 Cursor）。这个决定影响了它的架构和用户群体——更接近系统级工具，而非编辑器扩展。

### 关于 Worktree（2026年1月31日更新）

> "Spin up 3-5 git worktrees at once, each running its own Claude session in parallel. It's the single biggest productivity unlock, and the top tip from the team."

Worktree 比多个 git checkout 更优雅：
- 是 Claude Code 团队成员 @amorriscode 在 Claude Desktop app 里加了原生支持的原因
- 有工程师为 worktree 设置了 shell alias（`za`, `zb`, `zc`）一键跳转
- 有人专门设置一个"analysis worktree"只用于读日志和跑 BigQuery

### Plan Mode 的最佳实践（2026年1月31日）

> "Pour your energy into the plan so Claude can 1-shot the implementation. Don't keep pushing when things go sideways — switch back to plan mode and re-plan."

团队里有人：
- 一个 Claude 写计划 → 另一个 Claude 以 staff engineer 角色审
- 明确告诉 Claude 在验证阶段也进入 Plan mode，不只是在构建阶段

### CLAUDE.md 的进阶用法

> "After every correction, end with: 'Update your CLAUDE.md so you don't make that mistake again.' Claude is eerily good at writing rules for itself."

有工程师让 Claude 维护一个专门的 notes 目录（每个任务/项目一个文件，每次 PR 后更新），然后在 CLAUDE.md 里指向这个目录。

---

## 关键原则（分享给每位新成员）

Lenny's Podcast 中，Boris 提到他有 **3 条原则** 会和每个新成员分享。这部分是付费内容，完整版在 Lenny's Newsletter 订阅中，但从已有公开信息可以推断包含：

1. **验证循环优先**：给 Claude 一种验证自己工作的方式，这是获得好结果最重要的事
2. **CLAUDE.md 是团队的共同记忆**：每个错误都是一条规则，持续迭代
3. **计划比实现更重要**：在 Plan mode 投入精力，让 Claude 一次性实现

---

## 主要素材来源

| 类型 | 标题 / 链接 | 时间 |
|------|------------|------|
| 播客 | [Lenny's Podcast: Head of Claude Code — What happens after coding is solved](https://www.lennysnewsletter.com/p/head-of-claude-code-what-happens) | 2026年3月 |
| X Thread | [@bcherny 的 13 条工作流 tips（Jan 2 thread）](https://x.com/bcherny/status/2007179832300581177) | 2026-01-02 |
| X Thread | [@bcherny 的 10 条团队 tips（Jan 31 thread）](https://x.com/bcherny/status/2017742741636321619) | 2026-01-31 |
| X | [Auto Mode 公告](https://x.com/bcherny/status/2036555259997462541) | 2026-03-12 |
| X | [RAG vs Agentic Search](https://x.com/bcherny/status/2035385932342305067) | 2026-02 |
| 文章 | [VentureBeat: The creator of Claude Code just revealed his workflow](https://venturebeat.com/technology/the-creator-of-claude-code-just-revealed-his-workflow-and-developers-are) | 2026年1月 |
| 采访 | [Business Insider: Software engineering title may disappear](https://www.businessinsider.com/anthropic-claude-code-founder-ai-impacts-software-engineer-role-2026-2) | 2026年2月 |
| 采访 | [PCMag: Interview — It Was an Accident That Changed Everything](https://www.pcmag.com/news/interview-with-claude-code-creator-it-was-an-accident-that-changed-everything) | 2026年 |
| 汇总站 | [howborisusesclaudecode.com](https://howborisusesclaudecode.com/) | 社区整理 |

---

*最后更新：2026-03-25*
