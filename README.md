# Management Empirical Topic Builder

Management Empirical Topic Builder is a Codex Skill for generating evidence-based empirical management research topics from a Zotero literature collection.

It reads a specified Zotero Collection, subcollection, tag, saved search, or fallback bibliography/PDF corpus, then classifies papers, extracts findings and limitations, maps quantitative variable roles and qualitative mechanisms, synthesizes theory gaps, rebuilds variable networks, generates empirical model candidates, and evaluates topics from an SSCI management reviewer perspective.

## Author

- Author / Creator: 视频号「扣子说AI」
- Project: `management-empirical-topic-builder`

中文介绍见 [README.zh-CN.md](README.zh-CN.md).  
English introduction: [README.en.md](README.en.md).

## Installation

This repository is designed to be installed as a local Codex Skill.

1. Clone this repository:

```bash
git clone https://github.com/longkou1988/management-empirical-topic-builder.git
```

2. Copy or place the repository folder under your Codex skills directory:

```text
~/.codex/skills/management-empirical-topic-builder/
```

3. Make sure the final structure contains:

```text
~/.codex/skills/management-empirical-topic-builder/SKILL.md
~/.codex/skills/management-empirical-topic-builder/references/
~/.codex/skills/management-empirical-topic-builder/scripts/
```

4. Start a new Codex thread, or restart Codex if the Skill list has not refreshed.

5. If you want workbook template generation support, install the optional Python dependency:

```bash
pip install -r requirements.txt
```

## Usage

In Codex, call the Skill by name and specify the Zotero Collection, subcollection, tag, saved search, or fallback bibliography/PDF corpus you want to analyze.

Example:

```text
Use $management-empirical-topic-builder to analyze my Zotero Collection: entrepreneurship/women entrepreneurship
```

Chinese example:

```text
使用 $management-empirical-topic-builder 分析我的 Zotero Collection：创业相关/女性创业
```

You can also add constraints such as target journal direction, year range, country or region, industry context, theory lens, research method, or preferred empirical design.

## What It Produces

The Skill is designed to create these outputs under `output/` during use:

- `literature_matrix.xlsx`
- `variable_role_matrix.xlsx`
- `qualitative_mechanism_matrix.xlsx`
- `theory_gap_matrix.xlsx`
- `variable_network_summary.md`
- `topic_cards.md`
- `model_candidates.md`
- `final_research_story.md`
- `reviewer_evaluation.md`

## Core Principle

The Skill is evidence-first. It must not invent literature facts, variables, theoretical foundations, findings, DOI, journal names, or evidence text. Unsupported fields are explicitly marked as insufficient to judge.

## Repository Layout

```text
.
├── SKILL.md
├── README.md
├── README.zh-CN.md
├── README.en.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── analysis-rules.md
│   ├── extraction-schema.md
│   └── zotero-integration.md
└── scripts/
    └── create_workbook_templates.py
```

## License

MIT License. See [LICENSE](LICENSE).
