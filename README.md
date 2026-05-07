# 🔍 Tech Gap Checker

> 技术盲区扫描器——在你写第一行代码之前，先把整个项目缺的"零件"找出来。

## 问题

你说"帮我做一个聚会游戏，5个人各用自己手机编故事投票"，AI 就开始写代码。写完你发现：怎么没有房间系统？怎么不知道谁投了票？怎么没法部署？

**因为你不懂技术，你不知道要告诉 AI 做 Supabase Realtime、做 WebSocket、做 Vercel 部署。AI 也不会主动问你。**

## 这个 Skill 做什么

在你描述完项目想法后、AI 写任何代码前，自动扫描八个维度：

| 维度 | 检测什么 |
|------|----------|
| 多用户交互 | 需要实时同步吗？需要房间系统吗？ |
| 数据存储 | 用户数据存哪儿？刷新会丢吗？ |
| 用户系统 | 怎么区分用户？权限怎么管？ |
| 实时通信 | 一个人操作，其他人能立刻看到吗？ |
| 部署托管 | 前端放哪儿？后端放哪儿？免费额度够吗？ |
| 第三方服务 | 要 Supabase 吗？要支付吗？要 CDN 吗？ |
| 安全边界 | 输入会被注入吗？需要频率限制吗？ |
| 移动端体验 | 手机上能用吗？需要触屏适配吗？ |

每个维度输出三种标记：
- ✅ 已覆盖
- ⚠️ 盲区（你没提但必须有的）
- ❌ 不适用（说理由）

## 安装

### Codex

```bash
mkdir -p ~/.agents/skills/tech-gap-checker
cp SKILL.md ~/.agents/skills/tech-gap-checker/SKILL.md
```

然后在 `~/.codex/AGENTS.md` 的 Superpowers 路由规则下加一行：

```
- 新项目启动、用户描述要构建的应用/网站/游戏/工具：优先 `tech-gap-checker`，在写任何代码前扫描技术盲区，不等用户要求。
```

### Claude Code

```bash
mkdir -p ~/.claude/skills/tech-gap-checker
cp SKILL.md ~/.claude/skills/tech-gap-checker/SKILL.md
```

然后在 `~/.claude/CLAUDE.md` 的 Superpowers 自动路由下加一行：

```
- 新项目启动、用户描述要构建的应用/网站/游戏/工具：优先 `tech-gap-checker`，在写任何代码前扫描技术盲区，不等用户要求。
```

### 手动调用

如果你不想自动路由，只要 Skill 文件放在对应目录，对 AI 说"跑 tech-gap-checker"即可。

## 适用场景

- 你说"帮我做个 XX"但不知道背后需要哪些技术零件
- 让 AI 建项目后发现总是漏东西要补
- 不懂后端/运维/安全，但需要建完整可用的应用

## 原理

利用 AI 的 System 2 思维——在动手写代码之前，强制做一轮全局架构审查。类比：装修前先画水电图，而不是刷完墙才发现没布线。

## License

MIT
