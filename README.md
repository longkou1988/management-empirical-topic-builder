# Paper Topic Builder

Paper Topic Builder is a Codex Skill for generating evidence-based empirical paper topics from a Zotero literature collection. It is designed for management, entrepreneurship, organization studies, information systems, marketing, strategy, and related social science research.

The Skill reads a specified Zotero Collection, subcollection, tag, or fallback bibliography/PDF corpus, then classifies papers, extracts findings and limitations, maps quantitative variable roles, identifies qualitative mechanisms, synthesizes theory gaps, recombines variable networks, generates topic cards, and evaluates candidate topics from an SSCI-style reviewer perspective.

中文介绍见 [README.zh-CN.md](README.zh-CN.md). English guide: [README.en.md](README.en.md).

## Author

- Author: 视频号「扣子说AI」
- Purpose: help researchers turn Zotero literature collections into transparent, evidence-grounded empirical research topics.

## Install

Clone this repository into your Codex skills directory with the new Skill folder name:

```bash
git clone https://github.com/longkou1988/management-empirical-topic-builder.git ~/.codex/skills/paper-topic-builder
```

Restart Codex, then use the Skill name:

```text
$paper-topic-builder
```

If you installed the earlier local folder name `management-empirical-topic-builder`, rename it to `paper-topic-builder`.

## Usage

Example prompt:

```text
Use $paper-topic-builder to analyze my Zotero Collection: 创业相关/女性创业
```

You can also add constraints:

```text
Use $paper-topic-builder to analyze my Zotero Collection: digital entrepreneurship. Focus on theory gaps, quantitative variable roles, and SSCI topic ideas.
```

## Outputs

The Skill produces these files under `output/`:

1. `literature_matrix.xlsx`
2. `variable_role_matrix.xlsx`
3. `qualitative_mechanism_matrix.xlsx`
4. `theory_gap_matrix.xlsx`
5. `variable_network_summary.md`
6. `topic_cards.md`
7. `model_candidates.md`
8. `final_research_story.md`
9. `reviewer_evaluation.md`

## Quality Rules

- Zotero is used first when available.
- Exported `.bib`, `.ris`, `.csv`, or local PDFs are only fallback inputs.
- Literature facts, DOI, journal names, theories, variables, paths, and findings must come from Zotero metadata, abstracts, PDFs, notes, annotations, or fallback source files.
- Unsupported fields must be marked as insufficient evidence instead of being fabricated.
- Variable roles and model paths require evidence sections and confidence labels.

## License

MIT
