# Management Empirical Topic Builder 中文介绍

`management-empirical-topic-builder` 是一个面向管理学实证研究选题生成的 Codex Skill。它的核心用途是：基于 Zotero 文献库中的指定 Collection、子目录、标签或检索结果，系统读取文献证据，识别研究类型、变量角色、机制过程和理论缺口，并生成可进一步发展为 SSCI 管理学论文的实证选题。

## 适用场景

这个 Skill 适合用于：

- 从 Zotero 文献库中整理某一研究主题的文献矩阵；
- 判断文献属于定量、定性、混合方法、理论、综述、方法或元分析研究；
- 从定量论文中提取自变量、因变量、中介变量、调节变量、控制变量、假设路径和结果证据；
- 从定性论文中提取一阶概念、二阶主题、聚合维度、过程机制和边界条件；
- 总结理论缺口、机制缺口、情境缺口、方法缺口和变量角色缺口；
- 根据已有变量网络重组新的“前因-机制-结果-边界条件”模型；
- 生成不少于 10 个管理学实证论文选题；
- 从 SSCI 管理学期刊审稿人视角评价选题质量和发表风险。

## 工作流程

Skill 的默认流程包括：

1. 读取 Zotero Collection、子目录、标签、保存检索或文献列表；
2. 获取标题、作者、年份、期刊、DOI、摘要、关键词、标签、Collection 路径、备注、批注和 PDF 全文；
3. 判断文献类型并记录判断证据；
4. 抽取通用文献信息，生成 `literature_matrix.xlsx`；
5. 对定量研究抽取变量角色，生成 `variable_role_matrix.xlsx`；
6. 对定性研究抽取机制结构，生成 `qualitative_mechanism_matrix.xlsx`；
7. 综合理论缺口，生成 `theory_gap_matrix.xlsx`；
8. 建立变量网络并生成模型候选；
9. 生成选题卡片和排名前三的重点研究故事；
10. 从审稿人视角给出评分、风险和修改建议。

## 证据纪律

这个 Skill 强制遵守证据优先原则：

- 不编造文献事实、变量名称、理论基础、研究结论、DOI 或期刊信息；
- 所有变量角色必须有模型图、假设部分、方法部分、测量部分、结果表或讨论部分的证据；
- 如果只能读取摘要，必须标注“仅基于摘要分析”；
- 如果 PDF 缺失、不可读、乱码或权限不足，必须标注“全文不可用”；
- 不确定的信息必须标注“不足以判断”；
- 低置信度判断必须单独标注。

## 使用方式

在 Codex 中安装该 Skill 后，可以这样调用：

```text
使用 $management-empirical-topic-builder 分析我的 Zotero Collection：创业相关/女性创业
```

也可以指定更细的限制条件，例如年份、理论、目标期刊方向、国家地区、行业或研究方法。

## 输出文件

Skill 完成后会在 `output/` 下生成：

- `literature_matrix.xlsx`
- `variable_role_matrix.xlsx`
- `qualitative_mechanism_matrix.xlsx`
- `theory_gap_matrix.xlsx`
- `variable_network_summary.md`
- `topic_cards.md`
- `model_candidates.md`
- `final_research_story.md`
- `reviewer_evaluation.md`

## 注意事项

该 Skill 依赖 Zotero 插件读取文献库。只有在 Zotero 插件无法读取、权限不足、元数据缺失或全文无法访问时，才建议使用 `.bib`、`.ris`、`.csv` 或本地 PDF 文件夹作为 fallback。
