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

## License

MIT
