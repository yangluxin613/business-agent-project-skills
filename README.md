# Business Agent Project Skills

一组面向业务 Agent 项目的 Skills，按“确认需求 → 开发与验收 → 整理面试材料”组织。用户提供一项或多项过往业务经历或 PRD，先发散新的业务 Agent 产品机会，再围绕已确认的需求开展后续工作。过往需求是业务背景，不会被直接改名为 Agent 项目。

**本次只提供第一个 Skill：需求确认。**其余两个 Skill 后续发布，目前仓库不包含它们的文件。

| Skill | 状态 |
|---|---|
| [`business-agent-requirements`](business-agent-requirements/SKILL.md)：需求确认 | 本次提供 |
| `business-agent-development`：项目开发 | 后续发布 |
| `business-agent-interview`：面试材料 | 后续发布 |

## 使用需求确认 Skill

下载仓库后，在支持自定义 Skill 的 AI Agent 工具中，按该工具的导入方式加载 [`business-agent-requirements/`](business-agent-requirements/) 整个目录。至少保留 `SKILL.md` 和 `references/` 的相对目录结构。如果工具不支持目录导入，可将这些文件作为本轮对话的资料提供，并明确要求 AI 先阅读 `SKILL.md`，再按其中的指引读取相应参考文件。不同工具的安装路径和调用命令可能不同；下面使用不依赖特定命令的自然语言示例。

首次使用建议提供旧 PRD 或经历、你实际承担的工作、目标业务用户、可用数据或接口，以及资源约束。希望逐项规划技术方向时，同时附上[78 项技术方向清单](docs/business-agent-requirements/78项技术方向清单.md)：

```text
请使用 business-agent-requirements Skill，先执行 P00—P02。我会提供旧项目 PRD、本人职责和技术方向清单。旧需求只用于理解业务，不要直接改名为 Agent。请给出 3—5 个用户任务与结果形态不同的对话式业务 Agent 候选，标清原文事实、新产品假设和待确认项。到 P02 停止，不写代码。
```

先审阅候选并确认 P03 选题，再单独审阅、确认 P04 场景与验收条件。完整的物业模拟 PRD 和分阶段输入见[使用手册](docs/business-agent-requirements/使用手册.md)。

| 阶段 | 产物 | 需要确认什么 |
|---|---|---|
| P00—P01 | `source-experience.md` | 原文、本人职责与业务画像可追溯 |
| P02 | `opportunity-comparison.md` | 候选有不同用户任务和可核实结果 |
| P03 | `requirements-baseline.md` | 用户选定主用户、任务、MVP 与责任边界 |
| P04 | `scenario-and-acceptance.md`、`technology-requirements.md` | 对话、异常、人工接管与通过或失败条件 |
| 全程 | `project-state.md` | 版本、确认依据及待确认事项 |

对话、业务 Skill 和拟经 MCP 读取授权事实是候选设计的共同要求。RAG、Memory、知识图谱、多 Agent 等能力按业务场景分期，不因出现在技术清单中就宣称已实现。每项承诺接入的 AI 能力都应映射到用户消息、回复或动作、失败表现及未来验收证据。技术选型与接入验证由后续开发阶段完成。

## 本次发布内容

- [`business-agent-requirements/`](business-agent-requirements/)：需求确认 Skill 的完整文件，包括主指令和参考材料。
- [`docs/business-agent-requirements/使用手册.md`](docs/business-agent-requirements/使用手册.md)：合成物业旧 PRD 与 P00—P04 操作示例。
- [`docs/business-agent-requirements/78项技术方向清单.md`](docs/business-agent-requirements/78项技术方向清单.md)：用于规划和对账的技术方向，不是已实现声明。

本仓库采用 [MIT License](LICENSE)。请勿把真实客户资料、个人敏感信息或 API 密钥提交到仓库。模拟 PRD 的“确认”只适用于合成试跑，不等同于真实用户或客户确认。
