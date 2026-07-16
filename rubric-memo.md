# Rubric Memo — Bump 升级档案

> ⚠️ **本文件是 Channel A 内部参考。Channel B（cheat-score-blind sub-agent）永远不读本文件**——blind sub-agent 的 hard refusal list 显式包含本文件路径。
>
> 这里累积每次 rubric bump 的完整 Memo：触发观察、证据数据表（含真实样本名 + 实绩）、诊断、跨模型审核结论、已知局限。

---

## 这文件是干嘛的

cheat-bump Phase 5 落地时把升级 Memo 写**这里**，**不写**进 `rubric_notes.md`。

`rubric_notes.md` 是 blind sub-agent 的白名单文件——若把含实绩的 Memo 写进去，sub-agent 会通过它泄漏实绩数据，本应隔离的盲打分变成"看过实绩的事后解释"。

| 文件 | 内容 | blind 白名单 |
|---|---|---|
| `rubric_notes.md` | 公式 / 维度定义（**通用语言**，不含视频名 / 实绩）/ Bucket 段 | ✅ YES |
| `rubric-memo.md`（本文件） | 升级 Memo 全文（**含**真实视频名 + 真实播放数 + 派生证据） | ❌ NO（硬禁读） |

---

## Memo 段格式（cheat-bump 用此格式写）

每次 bump append 一段：触发观察 / 证据数据（校准池重打表，含真实视频名+实绩）/ 诊断 / 新公式 / 跨模型审核结论 / 已知局限。

---

## 例：v0 → v1（首次 bump）

（cheat-init 创建时本文件为空，首次 bump 时在此追加第一段 Memo）

<!-- 后续 bump 在此 append -->
