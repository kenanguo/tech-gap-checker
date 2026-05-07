# 🔍 Tech Gap Checker

> 一个专治"AI 写了代码但缺胳膊少腿"的 Skill。

---

## 你是不是也这样

你跟 AI 说："帮我做个聚会游戏，5个人各用手机编故事投票。"

AI 刷刷刷写了一堆代码。你打开一看——怎么没有房间系统？怎么不知道谁投了票？怎么还刷新就没了？部署又是啥？

**你不懂技术，你不知道要告诉 AI 做 Supabase Realtime、做 WebSocket、做部署。AI 也不会主动问你。**

然后你开始补。一个漏、两个漏、三个漏…你变成了项目经理，AI 变成了那个"你不说它就不做"的程序员。

---

## 这个 Skill 怎么救你

在你描述完项目想法后、AI 写第一行代码之前，它自动跑一轮全局扫描：

```
👤 你: 帮我做个聚会游戏，5个人各用手机编故事投票

🔍 Tech Gap Checker 自动扫描中...

📋 技术零件清单
✅ 前端网页：HTML/CSS/JS（你提了）
⚠️ 实时数据库：Supabase Realtime（盲区！5人投票需要状态同步）
⚠️ 房间系统：需要生成房间码+加入机制（盲区！）
⚠️ 部署：Vercel（前端）+ Supabase（后端）（盲区！都没提）
❌ 支付系统：首版不需要（随缘付费靠平台就行）

🔑 Top 3 盲区
1. Supabase Realtime — 没它，A投了票B看不到
2. 房间系统 — 没它，5个人没法进同一局
3. 部署方案 — 没它，代码写完了没人能访问

🛠️ 推荐方案：Vercel（免费）+ Supabase Realime（免费层200并发，够用）

要我按这个方案开始写代码吗？
```

**一秒钟，省掉两小时补漏。**

---

## 扫描什么（八个维度）

| 维度 | 它会问 |
|------|--------|
| 👥 多用户 | 各自操作还是同屏？需要房间吗？需要角色区分吗？ |
| 💾 数据存储 | 东西存哪儿？刷新会丢吗？需要数据库吗？ |
| 🔐 用户系统 | 怎么知道谁是谁？登录？昵称？权限？ |
| 📡 实时通信 | 一个人操作，其他人立刻看到吗？ |
| 🚀 部署托管 | 前端放哪儿？后端放哪儿？免费层够不够？ |
| 🧩 第三方服务 | 要 Supabase 吗？要支付吗？要图床吗？ |
| 🛡️ 安全边界 | 输入会被注入吗？需要防刷吗？ |
| 📱 移动端 | 手机上能用吗？触屏适配了吗？ |

每个维度三种输出：
- ✅ 已覆盖
- ⚠️ **盲区**（你没提、但项目运行必须有的）
- ❌ 不适用（说理由，不跳题）

---

## 安装（1 分钟）

### Codex

```bash
git clone https://github.com/kenanguo/tech-gap-checker.git /tmp/tech-gap-checker
mkdir -p ~/.agents/skills/tech-gap-checker
cp /tmp/tech-gap-checker/SKILL.md ~/.agents/skills/tech-gap-checker/
```

然后在 `~/.codex/AGENTS.md` 路由规则上加一行：

```
- 新项目启动、用户描述要构建的应用/网站/游戏/工具：优先 `tech-gap-checker`，不等用户要求。
```

### Claude Code

```bash
git clone https://github.com/kenanguo/tech-gap-checker.git /tmp/tech-gap-checker
mkdir -p ~/.claude/skills/tech-gap-checker
cp /tmp/tech-gap-checker/SKILL.md ~/.claude/skills/tech-gap-checker/
```

然后在 `~/.claude/CLAUDE.md` 路由规则上加一行：

```
- 新项目启动、用户描述要构建的应用/网站/游戏/工具：优先 `tech-gap-checker`，不等用户要求。
```

### 手动调用

不想配自动路由？Skill 文件放好就行。对 AI 说一句 **"跑 tech-gap-checker"** 即可。

---

## 谁需要这个

- 你懂产品不懂技术，让 AI 写代码但总漏东西
- 你让 AI 建了项目后发现要一直在补"你没想到的东西"
- 你不想学后端/运维/安全，但需要建完整可用的应用

---

## 为什么有用

AI 不会主动告诉你缺什么——它只做你让它做的事。

这个 Skill 在它动手之前，强制做一面"镜子"：你看不到的东西，它照出来。

> 装修前先画水电图，而不是刷完墙才发现没布线。

---

## License

MIT — 随便用，随便改，随便分发。
