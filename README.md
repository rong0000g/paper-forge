<div align="center">

# PaperForge 论文锻造

**证据优先的学术写作 Agent Skill：读文献、改论文、模拟审稿、投稿前检查、选刊——不编造任何文献、数据和结论。**

*An evidence-first academic writing skill for Codex & Claude Code — literature reading, paper restructuring, peer-review simulation, pre-submission checks and journal selection, with zero fabrication.*

[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-blue.svg)](LICENSE)
[![Codex Skill](https://img.shields.io/badge/Codex-Skill-black)](#codex)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-d97757)](#claude-code)
[![GitHub stars](https://img.shields.io/github/stars/rong0000g/paper-forge?style=social)](https://github.com/rong0000g/paper-forge/stargazers)

[中文](#中文) · [English](#english)

</div>

---

## 中文

### 为什么需要它

让 AI 帮忙写论文，最怕的不是写得不好，而是**写得“很像真的”**：编出不存在的文献、改掉你的结论、把推测写成实证。PaperForge 把“让 AI 生成内容”改造成一条**受证据约束、可追溯、可核验**的研究工作流——AI 只帮你重构和打磨，研究的实质始终是你的。

适合：硕博研究生、青年学者，尤其是用中文思考、要用中/英/外文投稿的海外留学生。

### 核心能力

| 场景 | PaperForge 会做什么 |
| --- | --- |
| 🔍 **证据与真实性** | 区分事实、推演与不确定信息；禁止编造文献、作者、DOI、数据、统计结果 |
| 📚 **文献阅读** | 用五层文献卡片重建研究问题、理论机制、识别策略、证据与局限，保留来源锚点，并建立可累计的研究账本 |
| ✍️ **写作前基准** | 先研究约 10–15 篇领域代表性论文，提炼论证结构、术语、句法和节奏，不复制原文 |
| 🛠 **结构重构与润色** | 不改变作者思路、数据和结论边界，做结构级重构和学术表达优化；避免机械化“AI 腔” |
| 🧩 **逻辑断点审计** | 十五点逻辑断点清单，重点查创新、方法复现、图表自解释性和结论越界 |
| 🧑‍⚖️ **模拟同行评审** | 按 `Major Comments`、`Minor Comments`、审稿人追问和最优先修改事项输出意见 |
| ✅ **投稿前检查** | 稿件、补充材料、投稿信、图表、元数据一致性扫描，引文逐条验真 |
| 🎯 **选刊** | 区分期刊资格、适配度、真实外审周期、费用与风险，建立冲刺—匹配—保底梯队 |

完整规则见 [`references/rules.md`](references/rules.md)，每条规则都有稳定编号（如 `R-E02 不编造`、`R-S02 十五点逻辑断点清单`、`R-J05 冲刺—匹配—保底梯队`）。

### 快速安装

> 保持目录名为 `paper-forge`，并完整复制整个仓库（`SKILL.md` 需要读取 `references/rules.md`）。

#### Codex

```powershell
# Windows PowerShell
git clone https://github.com/rong0000g/paper-forge.git "$env:CODEX_HOME\skills\paper-forge"
```

```bash
# macOS / Linux
git clone https://github.com/rong0000g/paper-forge.git "${CODEX_HOME:-$HOME/.codex}/skills/paper-forge"
```

如果未设置 `CODEX_HOME`，请使用本机 Codex 配置对应的 skills 目录。

#### Claude Code

```bash
git clone https://github.com/rong0000g/paper-forge.git ~/.claude/skills/paper-forge
```

Claude Code 应能从该目录发现 `SKILL.md`。若所用版本不支持自动发现，可在项目说明中显式要求读取 `SKILL.md`，并保留 `references/rules.md` 的相对路径。

#### 其他 Agent

把 `SKILL.md` 作为入口指令，并确保 Agent 能继续读取 `references/rules.md`。只复制入口文件，完整规则不会加载。

### 使用示例

直接对 Agent 说：

- “使用 `paper-forge` 修改这篇论文，但不要改变数据和核心结论。”
- “按同行评审框架检查创新点、方法复现、图表说明和结论越界，不要直接重写。”
- “为这个研究建立文献卡片和研究账本，并标出无法核实的信息。”
- “根据研究设计和近期同类论文建立冲刺、匹配、保底选刊梯队，同时核验费用与真实周期。”

### 输出长什么样

模拟审稿时，输出按规则 `R-R02` 的结构组织（以下仅为格式示意，非真实稿件意见）：

```text
Major Comments
1. [问题所在位置] → [为什么构成问题] → [建议的修改方向]
Minor Comments
1. ...
审稿人可能追问
- ...
最优先修改事项
- ...
```

涉及事实时会区分：**事实**（有原始材料或可复核计算支持）/ **推演**（基于证据的解释）/ **不确定**（明确写“无法核实”）。

### 设计边界

- 不替代作者对研究内容、数据真实性、伦理合规和最终署名的责任。
- 风格学习只提取可迁移机制，不复刻单篇论文措辞，不冒充具体学者。
- 不承诺录用率，不以规避 AI 检测或“去机器痕迹”为目标。
- 证据不足时，输出核验缺口，而不是补造一个看似完整的答案。

### 参与贡献

欢迎 Issue 和 PR！尤其欢迎：

- 补充或更正 `references/rules.md` 中的规则（请保持稳定编号、适用范围和清晰措辞）；
- 分享特定学科 / 特定期刊的使用经验（只适用于某个期刊的要求请注明，不写成全局规则）；
- 报告在 Codex、Claude Code 或其他 Agent 上的安装与兼容问题。

觉得有用的话，请点右上角 ⭐ Star 支持一下，这是让更多同学看到它的最好方式。

---

## English

**PaperForge** is a portable, evidence-first Agent Skill for academic work: literature reading, drafting and restructuring, translation and polishing, peer-review simulation, pre-submission checks and journal selection. It turns "let the AI generate text" into a traceable, verifiable research workflow.

### Features

- **No fabrication** – separates verified facts, evidence-based inference and uncertainty; never invents sources, DOIs, data, methods or results.
- **Literature cards** – five-layer cards that reconstruct research question, mechanism, identification strategy, evidence and limitations, with source anchors and a cumulative research ledger.
- **Field benchmarking** – studies ~10–15 representative papers to extract transferable structure, terminology and rhythm, without copying wording.
- **Author-preserving restructuring** – improves structure and academic prose without changing the author's ideas, data or claim boundaries.
- **15-point logic-gap audit** – novelty, method reproducibility, self-explanatory figures/tables, over-reaching conclusions.
- **Peer-review simulation** – `Major Comments`, `Minor Comments`, likely reviewer questions and top-priority fixes.
- **Pre-submission integrity checks** – consistency across manuscript, supplements, cover letter, figures and metadata; citation-by-citation verification.
- **Journal selection** – eligibility, fit, real review times, fees and risk; reach / match / safety tiers.

The full numbered rule set lives in [`references/rules.md`](references/rules.md) (written in Chinese; works with any language the agent handles).

### Install

```bash
# Codex
git clone https://github.com/rong0000g/paper-forge.git "${CODEX_HOME:-$HOME/.codex}/skills/paper-forge"
# Claude Code
git clone https://github.com/rong0000g/paper-forge.git ~/.claude/skills/paper-forge
```

Keep the folder name `paper-forge` and copy the whole repo – `SKILL.md` loads `references/rules.md`. For other agents, use `SKILL.md` as the entry instruction and make sure the agent can read `references/rules.md`.

### Usage

> "Use `paper-forge` to revise this paper without changing the data or core conclusions."
> "Review this manuscript with a peer-review framework – novelty, reproducibility, figures, over-claiming. Don't rewrite it."

### Boundaries

Not a substitute for the author's responsibility for content, data integrity, ethics and authorship. No acceptance guarantees, no AI-detection evasion, no impersonation of specific scholars.

### Contributing

Issues and PRs welcome – rule improvements, discipline/journal-specific notes, and compatibility reports. If it helps you, please ⭐ the repo.

## License

[GNU Affero General Public License v3.0](LICENSE) (AGPL-3.0-only). 公开分发修改版本或通过网络提供修改版本的功能时，须按许可证提供对应源代码并保留相同许可。
