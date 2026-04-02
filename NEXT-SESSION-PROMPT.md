# Next Session Prompt

直接复制下面这段：

```text
继续上次关于 Team Leader Agent / 多终端多子代理编排系统的探索。

先不要重新发散，也不要从头总结。请按下面顺序恢复上下文：
1. 读取 `.explore/teamleader-agent-orchestration-explore/handoffs/index.md`
2. 读取最新 handoff：`.explore/teamleader-agent-orchestration-explore/handoffs/2026-04-02-001-resume-ready.md`
3. 读取 `.explore/teamleader-agent-orchestration-explore/state.md`
4. 必要时再读取：
   - `.explore/teamleader-agent-orchestration-explore/workflow.md`
   - `.explore/teamleader-agent-orchestration-explore/decision-log.md`
   - `.explore/teamleader-agent-orchestration-explore/learnings.md`
   - `.explore/teamleader-agent-orchestration-explore/checkpoints.md`

恢复后先用 5-10 句话告诉我：
- 当前 mission 是什么
- 已完成了什么
- 当前关键结论是什么
- 现在可选的三条路线是什么

然后不要擅自扩写，先让我选择接下来走哪条路线：
- 路线 A：继续探索，输出一张详细对比表，按“可视化 / 上下文恢复 / 错误监控 / 并行冲突控制 / ACP 兼容 / 二开难度”比较相关项目和方案
- 路线 B：进入 proposal/design/tasks，收敛 Team Leader Agent 的 MVP 架构
- 路线 C：直接开始做 Team Leader Core 原型，先只做 worker 管理、心跳/错误监控、handoff 生成、git worktree 隔离

约束：
- 不要重复长篇背景介绍
- 不要重新检索已明确的基础信息，除非我要求更新
- 先基于已有 `.explore/` 记录继续
- 如果发现仓库状态与 handoff 不一致，先指出再继续
```
