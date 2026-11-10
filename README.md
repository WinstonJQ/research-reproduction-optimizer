# Research Reproduction Optimizer

## 项目简介

Research Reproduction Optimizer 是一套面向科研论文复现与实验优化的 Agent Skill，可在 Codex 及兼容 Agent Skills 的环境中使用。只需提供论文和对应的 GitHub 开源仓库，它就会围绕论文中的核心实验，协助完成资料获取、代码部署、Baseline 复现与结果核验，并在复现可信的基础上，进一步寻找能够提升性能的改进方向。

它的重点不只是让官方代码跑起来，而是建立一条高效、可重复的实验路径：从真实失败案例中寻找问题，广泛提出候选方案，用宽松的技术排雷和低成本预实验避免明显无效的投入，再对有潜力的方案进行公平验证与迭代组合。整个过程以实际涨点为优先目标，不因创新性暂时不足而过早放弃可行思路，也不为了凑够改进数量而夸大结果。

当实验取得进展后，Skill 会保留可复现的最佳版本、关键指标、有效改动、失败案例与实验记录，形成便于继续研究的证据材料。它的工作止于**实验改进的验证与成果交接**，不代替后续的科学问题提炼和论文创新论证。

## 安装

将整个 `research-reproduction-optimizer` 目录放到运行环境可识别的 Skills 目录。以 Codex 的常见用户级目录为例：

```bash
mkdir -p ~/.agents/skills
cp -R research-reproduction-optimizer ~/.agents/skills/
```

不同客户端的 Skill 路径可能不同，请以实际客户端配置为准。请确保 `SKILL.md` 与 `assets/handoff-template.md` 保持相对位置。

## 使用示例

```text
使用 $research-reproduction-optimizer 处理这篇论文。
论文：https://arxiv.org/abs/XXXX.XXXXX
GitHub：https://github.com/OWNER/REPO
数据集在 /data/xxx，优先复现主表 Ours。
环境允许使用现有 GPU，优先快速得到可信涨点。
```

也可以直接说明要从原有 `research_handoff.md` 和 `experiments.csv` 继续，避免重复部署与复跑。

## 职责边界

本 Skill 负责部署、复现、失败分析、筛选候选、执行涨点实验、冻结最优代码与交接证据。得到正向结果后，不额外组织论文贡献、理论框架或创新叙事。

运行时生成的 `research_handoff.md` 是下游分析可直接读取的事实材料，并不是 Skill 安装包中的预填结果。