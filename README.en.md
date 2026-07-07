# Management Empirical Topic Builder Introduction

`management-empirical-topic-builder` is a Codex Skill for generating evidence-based empirical management research topics from a Zotero literature collection.

Its purpose is to transform a specified Zotero Collection, subcollection, tag, saved search, or fallback bibliography/PDF corpus into structured literature matrices, variable-role maps, qualitative mechanism summaries, theory-gap analyses, model candidates, topic cards, and reviewer-style evaluations.

## Use Cases

This Skill is designed for researchers who need to:

- Build a structured literature matrix from a Zotero research collection;
- Classify papers as quantitative, qualitative, mixed-methods, theory, review, method, or meta-analysis papers;
- Extract independent variables, dependent variables, mediators, moderators, controls, hypotheses, tested paths, and empirical results from quantitative papers;
- Extract first-order concepts, second-order themes, aggregate dimensions, process mechanisms, and boundary conditions from qualitative papers;
- Identify theory gaps, mechanism gaps, boundary-condition gaps, context gaps, method gaps, conflicting results, and variable-role gaps;
- Recombine variable networks into coherent antecedent-mechanism-outcome-boundary models;
- Generate at least 10 empirical management research topic cards;
- Evaluate each topic from the perspective of an SSCI management journal reviewer.

## Workflow

The Skill follows this evidence-driven workflow:

1. Read the requested Zotero Collection, subcollection, tag, saved search, or item list;
2. Retrieve metadata, abstracts, tags, notes, annotations, attachment status, and PDF full text where available;
3. Classify each paper type using evidence from the paper;
4. Extract general literature information into `literature_matrix.xlsx`;
5. Extract quantitative variable roles into `variable_role_matrix.xlsx`;
6. Extract qualitative mechanisms into `qualitative_mechanism_matrix.xlsx`;
7. Synthesize theory gaps into `theory_gap_matrix.xlsx`;
8. Build a variable network and model candidates;
9. Generate topic cards and top-three research stories;
10. Score each topic using reviewer-style criteria.

## Evidence Discipline

The Skill is intentionally conservative. It must not fabricate literature facts, variable names, theories, findings, DOIs, journal names, or evidence text.

It explicitly marks:

- `仅基于摘要分析` when only metadata or abstract evidence is available;
- `全文不可用` when full text is missing, inaccessible, incomplete, or garbled;
- `不足以判断` when the available evidence is insufficient;
- `低置信度` when a judgment is weakly supported.

All quantitative variable-role extraction must be supported by evidence from model figures, hypotheses, methods, measurement sections, results tables, or discussion sections.

## Example Prompt

After installing the Skill in Codex, you can call it like this:

```text
Use $management-empirical-topic-builder to analyze my Zotero Collection: entrepreneurship/women entrepreneurship
```

You may also add focus constraints such as theory, journal set, country, industry, method, year range, or target journal direction.

## Outputs

The Skill produces the following files under `output/`:

- `literature_matrix.xlsx`
- `variable_role_matrix.xlsx`
- `qualitative_mechanism_matrix.xlsx`
- `theory_gap_matrix.xlsx`
- `variable_network_summary.md`
- `topic_cards.md`
- `model_candidates.md`
- `final_research_story.md`
- `reviewer_evaluation.md`

## Notes

This Skill is designed to use the Zotero plugin first. Fallback bibliography or PDF inputs should be used only when Zotero plugin access fails, permissions are insufficient, metadata is missing, or full text cannot be accessed through Zotero.
