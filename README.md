# PaperForge

**PaperForge（论文锻造）**是一套证据优先的可移植 Agent Skill，用于文献阅读、论文写作与重构、模拟同行评审、投稿前检查和选刊。它把“内容生成”改造成一条受证据约束、可追溯、可核验的研究工作流。

## 核心能力

- 区分事实、推演与不确定信息，禁止编造文献、数据、方法和结果。
- 写作前研究约 10–15 篇领域代表性论文，提炼论证结构、术语、句法和行文节奏，不复制原文。
- 用五层文献卡片重建研究问题、理论机制、识别策略、证据与局限，并保留来源锚点。
- 在不改变作者研究思路、数据和结论边界的前提下，进行结构级重构和学术表达优化。
- 执行十五点逻辑断点审计，重点检查创新、方法复现、图表自解释性和结论越界。
- 按 `Major Comments`、`Minor Comments`、审稿人追问和最优先修改事项输出模拟审稿意见。
- 检查稿件、补充材料、投稿信、图表和元数据之间的一致性，并逐条验证引文。
- 选刊时区分期刊资格、研究适配度、真实外审周期、费用和风险，不用宣传性平均时间代替证据。

## 文件结构

```text
paper-forge/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── rules.md
```

`SKILL.md` 定义触发条件和执行原则；`references/rules.md` 是完整、带稳定编号的规则集。

## 安装

### Codex

将整个仓库克隆或复制到 Codex skills 目录，并保持仓库目录名为 `paper-forge`：

```powershell
git clone https://github.com/15910095402/paper-forge.git "$env:CODEX_HOME\skills\paper-forge"
```

如果未设置 `CODEX_HOME`，请使用本机 Codex 配置所对应的 skills 目录。

### Claude Code

```bash
git clone https://github.com/15910095402/paper-forge.git ~/.claude/skills/paper-forge
```

Claude Code 应能从该目录发现 `SKILL.md`。若所用版本不支持自动发现，可在项目说明中显式要求读取 `SKILL.md`，并保留 `references/rules.md` 的相对路径。

### 其他 Agent

把 `SKILL.md` 作为入口指令，并确保 Agent 可以继续读取 `references/rules.md`。不要只复制入口文件，否则完整规则不会加载。

## 使用示例

- “使用 `paper-forge` 修改这篇论文，但不要改变数据和核心结论。”
- “按同行评审框架检查创新点、方法复现、图表说明和结论越界，不要直接重写。”
- “为这个研究建立文献卡片和研究账本，并标出无法核实的信息。”
- “根据研究设计和近期同类论文建立冲刺、匹配、保底选刊梯队，同时核验费用与真实周期。”

## 设计边界

- 本 Skill 不能替代作者对研究内容、数据真实性、伦理合规和最终署名的责任。
- 风格学习仅提取可迁移机制，不复刻单篇论文措辞，不冒充具体学者。
- 不承诺录用率，不把 AI 检测规避或“去机器痕迹”作为目标。
- 当证据不足时，输出核验缺口，而不是补造一个看似完整的答案。

## License

本项目采用 [GNU Affero General Public License v3.0](LICENSE)（AGPL-3.0-only）。公开分发修改版本，或通过网络向用户提供修改版本的功能时，必须按许可证要求提供对应源文件并保留相同许可。

