# Zotero Integration

Use this file before literature intake. The confirmed Zotero plugin Skill is:

`/Users/long/.codex/plugins/cache/openai-curated-remote/zotero/0.1.2/skills/zotero/SKILL.md`

Read that Skill first and follow its current instructions. Do not invent Zotero function names.

## Confirmed Helper

The confirmed helper script is:

```bash
python3 /Users/long/.codex/plugins/cache/openai-curated-remote/zotero/0.1.2/skills/zotero/scripts/zotero.py <command>
```

Start every Zotero-backed run with:

```bash
python3 /Users/long/.codex/plugins/cache/openai-curated-remote/zotero/0.1.2/skills/zotero/scripts/zotero.py status --json
```

If Zotero local API access is disabled and the user has asked to operate Zotero, use the Zotero Skill's enable flow, including restart, before falling back to exported files.

## Discovery Commands

Use the helper's actual commands and help output. Known read-only commands include:

- `collections --json` to inspect collections.
- `tags --json` to inspect tags.
- `selected-target --json` to inspect the currently selected Zotero target when useful.
- `inventory --include-children --json` to inspect library items and attachments.
- `search "<query>" --json` to search items.
- `children <itemKey> --json` to list a parent item's attachments/notes.
- `fulltext <attachmentKey> --out <path>` to retrieve indexed attachment text.
- `file-url <attachmentKey>` to resolve an attachment file URL when needed.
- `export-bibtex --item-key <itemKey> --include-children --out <path>` for bibliographic fallback capture.

The workflow may retrieve attachment keys, attachment file URLs, and full text because the user explicitly requested PDF/full-text evidence extraction.

## Scope Resolution

When the user specifies a Collection, subcollection, saved search, tag, or item list:

1. Try the Zotero helper commands first.
2. If the helper output does not directly expose the requested scope or item membership, read the plugin route reference at:
   `/Users/long/.codex/plugins/cache/openai-curated-remote/zotero/0.1.2/skills/zotero/references/local-api-routes.md`
3. Use only documented safe read-only local API routes from that file. Do not rely on undocumented endpoints unless the Zotero Skill or current helper help explicitly documents them.
4. If exact scope membership still cannot be resolved, stop and report the specific gate, then request a fallback `.bib`, `.ris`, `.csv`, or local PDF folder.

## Required Provenance Fields

For every paper, preserve where each fact came from:

- `Zotero metadata`
- `Zotero abstract`
- `Zotero note`
- `Zotero annotation`
- `PDF full text`
- `PDF indexed full text`
- `Fallback BibTeX/RIS/CSV`
- `Fallback local PDF`

If collection path is not returned by the helper/API and cannot be derived from confirmed collection membership evidence, write `不足以判断` rather than inferring it.

## Failure Labels

Use these exact labels where relevant:

- `仅基于摘要分析`
- `全文不可用`
- `附件缺失`
- `全文缺页`
- `全文乱码`
- `权限不足`
- `低置信度`
- `不足以判断`
