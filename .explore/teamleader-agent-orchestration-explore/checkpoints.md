# Checkpoints

## 2026-04-02 - 初始探索总结

### 当前阶段
- 路由一：纯探索 / 需求梳理 / 方案比较

### 本轮完成内容
- 明确了目标系统是一个 Team Leader / Orchestrator，而非单一 coding agent。
- 梳理了用户关注点：多终端调度、上下文恢复、错误监控、并行冲突、交接和人工接管。
- 评估了 Claude Code agent teams、subagents、Zed、ACP/acpx、myclaude 的定位。
- 额外扩展调研了一组更接近控制平面或底座的项目：Contrabass、fab、Angy、Agent Swarm、OpenCastle、metaswarm、OpenHands SDK、LangGraph、OpenAI Agents SDK、Temporal、process-compose、Overmind、tmuxp。
- 形成了“控制平面 + 执行平面 + 通信层 + 状态层 + 锁管理”的分层思路。

### 本轮决策与原因
- 不直接押注单一现成框架，优先考虑“借鉴架构，自写新壳”。
- 控制平面应自持状态和仲裁逻辑，执行平面可兼容不同模型或代理后端。
- 第一阶段更适合做 MVP，而不是一次性做平台化全功能系统。

### 本轮沉淀经验
- 真正的难点不在“多 agent”本身，而在“恢复、锁、冲突、人工接管、可回放性”。
- 对这类系统，先把状态真相源和事件流设计好，后续替换执行器会轻松很多。

### 待解决问题
- 先做 MVP 还是先做完整 proposal。
- 是否以 ACP 为一等协议，还是先用本地进程和文件事件打底。
- 是否需要优先做可视化 dashboard。

### 下一步
- 二选一：
- 继续探索并输出选型对比表。
- 进入 proposal/design/tasks，定义 MVP 架构和实现边界。

### 可以从活跃上下文移除的内容
- 大量项目背景介绍和重复比较过程可以遗忘。
- 当前只需记住关键项目定位和推荐路线即可。
