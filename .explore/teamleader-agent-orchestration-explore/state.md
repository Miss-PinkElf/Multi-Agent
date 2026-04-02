# 当前状态

## 当前阶段
- 路由一：纯探索 / 需求梳理 / 方案比较

## 已确认的事实
- 用户想要一个外层 Team Leader Agent，用来指挥多个子终端/子代理执行任务。
- 用户的核心诉求不是再增加一个写代码的 agent，而是增加调度、监督、恢复与冲突控制能力。
- 用户偏好多终端协作，希望有“指挥终端”统一分派“这个终端干这个，那个终端干那个”。
- 用户明确关注上下文太长后的重开续接、错误监控、并行冲突、优先级、任务交接与记录。
- 已讨论的相关方向包括 Claude Code agent teams、Claude subagents、Zed、ACP / acpx、myclaude。
- 额外检索到的相关项目包括 Contrabass、fab、Angy、Agent Swarm、OpenCastle、metaswarm、OpenHands SDK、LangGraph、OpenAI Agents SDK、Temporal、process-compose、Overmind、tmuxp。
- 初步判断：Claude Code agent teams 更适合作为参考，不适合作为长期唯一底座；Zed 更适合 UI/观察面；ACP/acpx 更适合作为通信层；SQLite + JSONL + worktree + locks 更适合作为状态和并行控制底座。

## 工作假设
- 真正可用的系统应拆分为控制平面和执行平面，而不是把所有逻辑塞进某个单一 agent 团队框架。
- 第一版最适合先做 MVP：启动 worker、记录状态、监控错误、生成 handoff / reopen context、隔离并行写入。
- 若需要长期演化，借鉴现有开源项目的架构比重度依赖某一个具体项目更稳妥。

## 待解决的问题
- 用户更偏向“快速做一个能用的原型”，还是“做成可长期演进的平台”。
- 是否需要优先兼容 ACP 协议，还是先用 shell/tmux/JSONL 本地模式验证。
- 是否需要从现有开源项目直接 fork，还是只借鉴设计思路。
- 可视化界面是先要 TUI、Web dashboard，还是先仅做状态文件和日志。

## 下一步
- 恢复后先读取最新 handoff 和本 mission 的 state/workflow。
- 然后让用户在三条路线中选一条继续：
- 路线 A：继续探索并输出对比表，按“可视化 / 上下文恢复 / 错误监控 / 并行冲突控制 / ACP 兼容 / 二开难度”评分。
- 路线 B：进入 proposal/design/tasks，收敛 MVP 架构。
- 路线 C：直接做 Team Leader Core 原型，功能限定为 worker 管理、心跳/错误监控、handoff 生成、worktree 隔离。

## 最新 handoff
- `handoffs/2026-04-02-001-resume-ready.md`

## 最小活跃上下文摘要
- 目标是探索一个多终端 Team Leader Agent。
- 当前结论偏向“自研控制平面 + 借鉴现有项目架构”，而不是直接押注某个现成框架。
- 最值得深入借鉴的项目/方向：Contrabass、Agent Swarm、Angy、OpenHands SDK、Temporal。
- 需要进一步决定是走“快速 MVP”还是“平台化设计”路线。
