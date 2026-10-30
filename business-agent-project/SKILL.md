---
name: business-agent-project
description: 从业务经历或 PRD 确认对话式业务 Agent 需求，按已确认需求开发并逐阶段验收，或依据真实项目证据撰写 Agent 岗面试材料。适用于 P00—P14 的任一指定阶段，也适用于用户明确要求的全流程；根据“需求、开发、面试”意图只加载对应参考文件。
---

# 业务 Agent 项目：需求、开发、面试

这是一个有三种模式的 Skill。先判断用户本轮要完成什么，只执行该模式中用户指定的单元及直接前置核对。三种模式共享项目工作区中的需求、状态与证据文件，不通过聊天摘要代替交接。用户明确要求全流程时按需求 → 开发 → 面试推进；阶段门禁仍分别生效。

| 用户意图或阶段 | 模式 | 首先读取 |
|---|---|---|
| 过往经历/PRD、业务机会、产品选题、场景与验收；P00—P04 | **需求** | [机会与基线](references/requirements/opportunity.md)、[业务产品与场景](references/requirements/business-product.md)；交接时读[需求包契约](references/requirements/handoff.md) |
| 架构、页面/API/状态、代码、模型/RAG/MCP/Memory、测试与验收；P05—P13 | **开发** | 先读[开发输入与证据契约](references/development/handoff.md)，再按具体单元读取下表的开发参考文件 |
| 项目叙事、面试问答、Markdown 简历、海报/展示；P14A—P14G | **面试** | 先读[面试证据契约](references/interview/handoff.md)，再按具体产物读取下表的面试参考文件 |

用户明确说“需求/开发/面试”或给出阶段编号时照此选择。未给模式时按当前任务选择；“继续”则先读 project-state.md 和当前单元验收卡，再继续未完成且前置已满足的单元。只有模式确实无法判断、且不同选择会改变产物时，简短询问。一次请求不要把“选题、写代码、写简历”混成同一输出；除非用户明确要求全流程，否则在指定单元完成后停止。

## 需求模式：P00—P04

读取用户原始经历和已有项目状态。旧 PRD 是业务背景，不自动改名为 Agent 产品；从原业务的用户目标、对象、资料、判断和异常发散不同机会，不预设待办、审核或任务台。P02 候选都要有业务人员可用的对话入口、具体回复、追问、业务 Skill 与拟用 MCP 数据落点，以及可核实的业务结果。仅业务需要时设计审批或待办。

把原文事实、合理推断、新产品假设和已确认决定分开记录；最多问五个真正会改变选题或 MVP 的问题，继续可独立完成的草案。用户只要机会比较时停在 P02。P03 确认选题基线，P04 **另行**确认场景、业务结果证据和验收意图；P03 确认不能代替 P04。未获相应确认的产物标草案或待确认，不向开发模式交付为已冻结需求。标准产物及路径映射见[需求包契约](references/requirements/handoff.md)。

若用户明确要求用模拟历史 PRD 跑全流程，可分别记录 P03、P04 的**模拟确认**，仅供隔离合成原型试跑；所有状态与对外材料持续标“合成试跑”，真实项目仍需真实业务确认。

## 开发模式：P05—P13

先核对 project-state.md、P03 与 P04 各自的版本和确认依据，再读取需求包、已有代码和验收记录。缺关键业务决定时可写标假设的技术草案；依赖它的实现和验收不得标通过。已有项目可从指定阶段进入，只核对直接前置条件。按用户指定的单元读取：

| 单元 | 参考文件 |
|---|---|
| P05—P06 技术覆盖、架构、页面/状态/API | [技术架构与规格](references/development/architecture-spec.md)、[技术目录](references/development/technology-catalog.md) |
| P07—P08 合成验收集与首个业务闭环 | [业务 MVP](references/development/business-mvp.md) |
| P09 一个相邻业务场景 | [场景增量](references/development/scenario-increment.md) |
| P10A 模型、Prompt、业务 Skill、Tool Calling | [模型与工具](references/development/model-tools.md) |
| P10B Wiki、RAG、重排、图谱 | [知识检索](references/development/knowledge-rag.md) |
| P10C MCP、Context、Memory | [MCP/上下文/记忆](references/development/mcp-context-memory.md) |
| P10D 多 Agent、Loop、恢复 | [协作编排](references/development/orchestration.md) |
| P11A 外部系统、Mock、平台 | [系统集成与平台](references/development/external-platform.md) |
| P11B 推理选型、性能与生产保障 | [推理与运行](references/development/inference-production.md) |
| P12—P13 评估、观测、技术审计 | [评估与验收](references/development/evaluation-acceptance.md)、[技术目录](references/development/technology-catalog.md) |
| 状态、验收卡、证据交接 | [项目状态](references/development/project-state.md)、[开发输入与证据契约](references/development/handoff.md) |

主依赖是已确认 P03/P04 → P05 → P06 → 冻结 P07 → P08。P09 一次扩一个场景，P10—P11 按业务依赖分批接入。每个承诺实施的单元**开工前**固定验收卡：主路径、失败/越权路径、禁止副作用和受影响旧流程；完成后运行测试和适用的前端操作，记录命令或点击、输入、环境、版本、预期/实际、Trace、修复与复测。只标通过、失败或待验收；依赖失败时不能把下一单元写成完成。

技术覆盖按用户要求逐项映射业务功能、用途、边界、阶段和证据。对每项承诺接入的 AI 能力，再记录用户消息、介入点、回复或动作变化、失败表现与同一请求的后台证据。合成数据、Mock、真实模型调用、MCP、外部系统和生产环境分别验收。P08 的 Mock 闭环不代替完整产品要求的实际模型、Skill 或 MCP 调用证据。开发输出、技术状态和证据轴见[开发输入与证据契约](references/development/handoff.md)。

## 面试模式：P14A—P14G

可从现成项目直接进入，不要求重跑需求或开发阶段。读取用户真实任职与本人职责、可公开范围，以及需求、代码、验收卡、运行环境、Trace/测试和 P13 技术状态。按任务读取：

| 单元 | 参考文件 |
|---|---|
| P14A—B 事实锁定与项目叙事 | [证据与叙事](references/interview/evidence-narrative.md) |
| P14C—E 技术目录、问答和 Markdown 简历 | [面试与简历](references/interview/interview-resume.md) |
| P14F—G 海报、展示与最终复核 | [展示与复核](references/interview/showcase-review.md) |

先建 claim-ledger.md，逐条记来源、环境、本人贡献、准确措辞、可用范围与缺口。技术问答只写有代码和运行证据的已接入或局部能力；仅选型、未接入或无证据的技术不得写成落地经验。成果数字需有样本、分母、时段和测量方法。简历、问答与展示材料逐句回指台账。发现证据缺口时标待核验，并继续写有证据的部分；不得用写作补齐实现。模拟 PRD 试跑只能写独立合成试验，不能自动写入过去雇主经历。具体门禁见[面试证据契约](references/interview/handoff.md)。

## 三种常用调用

- **确认需求：**“使用 `$business-agent-project` 的需求模式，读取我的旧 PRD，只做 P00—P02，给出不同业务任务的 Agent 候选；停在候选比较。”
- **开发项目：**“使用 `$business-agent-project` 的开发模式，核对 P03/P04 确认与当前状态，只做 P05；先写技术覆盖和架构，完成后停止。”
- **准备面试：**“使用 `$business-agent-project` 的面试模式，核对现有项目的代码、测试和本人职责，只写有证据的项目叙事与问答；缺证处标待确认。”

这些是同一个 Skill 的三种自然语言调用方式，不依赖特定平台的三个独立斜杠命令。跨模式交接仍由项目文件和确认/验收门禁控制。
