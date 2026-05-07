# 🔍 Tech Gap Checker

> 写代码之前，先把你项目里藏着的技术盲区全部扫出来。

---

## 谁需要这个

你懂产品、懂业务，但不太懂后端/运维/安全。你跟 AI 说"帮我做一个 XX"，AI 写了代码——但你总发现要补东西：怎么存数据？怎么部署？多个人同时用怎么办？

这个 Skill 就是补你不需要懂的那部分。你负责说"做什么"，它负责说"还缺什么"。

---

## 它做什么

在你描述完项目、AI 动手写代码之前，自动扫描八个维度：

| 维度 | 会追问 |
|------|--------|
| 👥 多人交互 | 各自操作还是同屏？需要房间吗？需要实时同步吗？ |
| 💾 数据存储 | 数据存哪儿？刷新会丢吗？需要数据库吗？ |
| 🔐 用户系统 | 怎么区分用户？需要登录吗？权限怎么管？ |
| 📡 实时通信 | 一个人操作，其他人需要立刻看到吗？ |
| 🚀 部署托管 | 前端放哪儿？需要后端吗？免费额度够吗？ |
| 🧩 第三方服务 | 要数据库服务吗？要支付吗？要图床吗？ |
| 🛡️ 安全边界 | 用户输入安全吗？需要限流吗？ |
| 📱 移动端 | 手机上能用吗？需要触屏适配吗？ |

每个维度三种输出：✅ 你提了  ‖  ⚠️ 你没提但项目需要  ‖  ❌ 不适用（说理由）

最后给一份**推荐技术选型**，标注免费额度，直接能用。

---

## 效果

扫完后你会看到：

```
📋 技术零件清单
✅ 前端框架：React（你提了）
✅ 托管平台：Vercel（你提了）
⚠️ 数据库：用户内容需要持久化（盲区）
⚠️ 用户认证：需要区分不同用户（盲区）
⚠️ 文件上传：需要图床/对象存储（盲区）
❌ 支付系统：当前不需要
❌ 实时通信：纯展示类，不需要

🔑 Top 3 盲区
1. 数据库 — 不存起来，刷新就没了
2. 用户认证 — 不知道谁提交了什么
3. 文件存储 — 用户上传的图需要有地方放

🛠️ 推荐方案：Vercel + Supabase（免费层 500MB 数据库 + 文件存储）
```

---

## 安装

### Codex

```bash
git clone https://github.com/kenanguo/tech-gap-checker.git /tmp/tech-gap-checker
mkdir -p ~/.agents/skills/tech-gap-checker
cp /tmp/tech-gap-checker/SKILL.md ~/.agents/skills/tech-gap-checker/
```

在 `~/.codex/AGENTS.md` 加一行：

```
新项目启动：优先 `tech-gap-checker`，写代码前扫描技术盲区。
```

### Claude Code

```bash
git clone https://github.com/kenanguo/tech-gap-checker.git /tmp/tech-gap-checker
mkdir -p ~/.claude/skills/tech-gap-checker
cp /tmp/tech-gap-checker/SKILL.md ~/.claude/skills/tech-gap-checker/
```

在 `~/.claude/CLAUDE.md` 加一行同上。

不想配自动路由？Skill 放好后对 AI 说一句 **"跑 tech-gap-checker"** 即可。

---

## 原理

AI 写代码默认是 System 1——直觉快反应，你说啥它写啥。

这个 Skill 强制它先跑一轮 **System 2**——慢思考、全局审查、把看不见的东西照出来。

> *"Thinking, Fast and Slow" — Daniel Kahneman*

---

## English

# 🔍 Tech Gap Checker

> Before AI writes a single line of code, scan your project for every hidden technical gap.

---

## Who needs this

You know product and business, but not backend, DevOps, or security. You tell AI "build me an app that does X" — AI writes the code, but you always find yourself patching holes: where does the data go? How do I deploy it? What if multiple people use it at once?

This Skill fills in what you shouldn't have to know. You say *what* to build. It says *what's missing*.

---

## What it does

Before AI starts coding, it automatically scans eight dimensions:

| Dimension | What it asks |
|-----------|-------------|
| 👥 Multi-user | Separate devices or shared screen? Rooms? Real-time sync? |
| 💾 Data storage | Where does data live? Survives a refresh? Database needed? |
| 🔐 User system | How to tell users apart? Login or nickname? Permissions? |
| 📡 Real-time | Should one user's action appear instantly for others? |
| 🚀 Deployment | Frontend where? Backend where? Enough free tier? |
| 🧩 Third-party | Database service? Payments? Image hosting? AI APIs? |
| 🛡️ Security | Input sanitization? Rate limiting? Sensitive data handling? |
| 📱 Mobile | Works on phones? Touch gestures? Portrait vs landscape? |

Each dimension gets one of three flags: ✅ covered  ‖  ⚠️ gap (you didn't mention, but the project needs it)  ‖  ❌ not applicable (with reason)

Then it delivers a **recommended tech stack** with free tier limits — ready to use.

---

## What you get

After scanning, you'll see:

```
📋 Parts Checklist
✅ Frontend: React (mentioned)
✅ Hosting: Vercel (mentioned)
⚠️ Database: user content needs persistence (gap)
⚠️ Auth: need to distinguish users (gap)
⚠️ File storage: user uploads need a home (gap)
❌ Payments: not needed for now
❌ Real-time: read-only content, not needed

🔑 Top 3 Gaps
1. Database — without it, everything vanishes on refresh
2. Auth — can't tell who submitted what
3. File storage — uploaded images need somewhere to live

🛠️ Recommended: Vercel + Supabase (free tier: 500MB database + file storage)
```

---

## Install

### Codex

```bash
git clone https://github.com/kenanguo/tech-gap-checker.git /tmp/tech-gap-checker
mkdir -p ~/.agents/skills/tech-gap-checker
cp /tmp/tech-gap-checker/SKILL.md ~/.agents/skills/tech-gap-checker/
```

Add to `~/.codex/AGENTS.md`:

```
New project: run `tech-gap-checker` before writing any code.
```

### Claude Code

```bash
git clone https://github.com/kenanguo/tech-gap-checker.git /tmp/tech-gap-checker
mkdir -p ~/.claude/skills/tech-gap-checker
cp /tmp/tech-gap-checker/SKILL.md ~/.claude/skills/tech-gap-checker/
```

Add to `~/.claude/CLAUDE.md` with the same routing rule.

No auto-routing? Just tell your AI: **"run tech-gap-checker"**

---

## How it works

AI defaults to **System 1** — fast, intuitive, does exactly what you asked.

This Skill forces a **System 2** pass first — slow, deliberate, scanning the whole picture for what's invisible.

> *"Thinking, Fast and Slow" — Daniel Kahneman*

---

## License

MIT
