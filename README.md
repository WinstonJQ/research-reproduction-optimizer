# Research Reproduction Optimizer

这是一个用于 Codex/兼容 Agent Skills 的科研复现与实验涨点 Skill。

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