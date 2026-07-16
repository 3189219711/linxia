# 工作流速查（cheat-on-content）

> `/cheat-init` 在项目根创建的速查文档。完整规范在 `~/.kiro/skills/cheat-on-content/SKILL.md` 和 `shared-references/`。
> 忘了下次该说什么时看这里。

---

## 一句话流程

```
找选题（cheat-seed brainstorm / 抓热点）
  ↓
写草稿 → scripts/<日期>_<id>_<short>.md
  ↓
打分（探索）→ "打分这篇 scripts/<...>.md"
  ↓
盲预测（承诺，写不可变日志）→ "启动预测 scripts/<...>.md" → predictions/
  ↓
拍摄 → "拍了 scripts/<...>.md" → 建 videos/<...>/ + buffer +1
  ↓
发布 → "已发布 https://..." → buffer -1
  ↓
T+3 天 → "复盘 videos/<...>/" → 抓数据 + 追加 ## 复盘 段
  ↓
累计 ≥3 同向偏差 → "升级 rubric"（全量重打 + 跨模型审）
```

---

## 五个阶段对应触发词

| 阶段 | 想做什么 | 说 |
|---|---|---|
| 选题 | 看推荐 / 抓热点 / 看状态 | "推荐选题" / "抓热点" / "状态" |
| 打分 | 探索性看 rubric 分（无副作用） | "打分这篇 scripts/xxx.md" |
| 预测 | 给最终稿写不可变预测 | "启动预测 scripts/xxx.md" |
| 拍摄登记 | 拍完了 | "拍了 scripts/xxx.md" |
| 发布登记 | 发完了 | "已发布 https://..." |
| 复盘 | T+3 天数据来了 | "复盘 videos/xxx/" 或 "复盘" |
| 升级 | 累计 3 次同向偏差 | "升级 rubric --propose '...'" |

---

## 三条不可妥协的原则

1. **盲预测**：预测段写在看到任何数据之前，写完不可改。
2. **升级 = 全量重打**：bump 必须校准池全量重打分 + 跨模型独立审。
3. **rubric 是工作台不是博物馆**：被吸收 / 被推翻的观察都删掉，git history 是档案。

---

## ⚠️ Kiro 环境说明（与原版 Claude Code 的差异）

- 本技能原生为 Claude Code / Codex 设计。在 Kiro 里，原来的 `.claude/settings.json` hooks 不生效。
- 等效的两个 **Kiro Agent Hooks** 已配好：
  - **Cheat 预测不可变保护**（preToolUse）— 写入前拦截对 predictions/ 里预测段的修改。
  - **Cheat 状态看板**（userTriggered）— 在 Agent Hooks 面板手动点触发，等效于说"状态"。
- 数据回收用 adapter，但 adapter 尚未安装（`pending_adapter_setup: true`），第一次发布前装 `douyin-session`。

---

## 你的项目当前配置

| 设置 | 值 |
|---|---|
| 内容形态 | opinion-video（观点视频，匹配内置 rubric）|
| 典型时长 | ~90 秒 |
| 发布节奏 | 日更（buffer 断更监控开启）|
| 数据回收 | adapter（douyin-session，待装）|
| 对标账号 | 无（v0 等权 rubric 起步）|
| 校准样本 | 0 / 5（cold-start）|
| rubric 版本 | v0 |
