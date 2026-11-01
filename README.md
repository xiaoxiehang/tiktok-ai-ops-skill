# TikTok AI Ops Skill

A self-improving playbook (an agent "skill") for running a TikTok account built on AI-generated short videos.
It is written for AI agents (Claude-style `SKILL.md`), but humans can read it as a checklist.

一个会自我进化的 TikTok AI 短视频运营技能。给 AI 智能体用（`SKILL.md` 格式），人也可以当清单读。

## What's inside / 内容

- **Operating loop / 运营循环**: learn daily -> distill into the playbook -> produce & post -> weekly review.
  每天学习 → 沉淀进手册 → 制作发布 → 每周复盘。
- **Niche selection with data / 用数据选赛道**: why recurring original AI characters and series beat one-off viral clips.
  为什么"原创固定角色 + 连载"比单条爆款更能涨粉。
- **First-second retention / 开头 1 秒留人**: frame-0 rules, hook text placement, loop endings, template fatigue.
- **AI video production / AI 视频制作**: start frame -> image-to-video -> QA -> ffmpeg; a six-part video prompt method.
- **Hard boundaries / 硬性边界**: AI label on every post, original characters only, no explicit content, no paid tools.

## How to use / 使用方法

1. Drop `SKILL.md` into your agent's skills folder (e.g. `.claude/skills/tiktok-ai-ops/SKILL.md`).
   把 `SKILL.md` 放进智能体的技能目录。
2. Give the agent two daily jobs: a learning run that updates the playbook, and a production run that follows it.
   给智能体两个每日任务：一个学习并更新手册，一个按手册制作发布。
3. Keep a private notes log and character reference images next to it; never put account data in the public copy.
   账号数据和角色参考图放在私有笔记里，不要放进公开版本。

## Updates / 更新

The playbook is updated from a live account's daily learning loop. See `CHANGELOG.md`.
手册随实账号每日学习持续更新，见 `CHANGELOG.md`。

Rules carry their evidence and date; treat platform numbers as snapshots, not guarantees.
每条规则都注明证据和日期；平台数据是当时的快照，不是保证。

## License

MIT. The video-prompt section is adapted from [sunfjun/claude-skill-ai-video-prompt](https://github.com/sunfjun/claude-skill-ai-video-prompt) (MIT).
