# Commit Message Guidelines

> Consistent commit messages = readable history = better portfolio signal.

## Format

```
<scope>: <imperative summary>

[optional body: what & why, not how]

[optional footer: refs, decisions]
```

## Scope (use one)

- `geo-sprint` — GEO sprint project work
- `notes` — learning notes
- `medical-nlp` — future medical NLP project
- `education-recsys` — future education recsys project
- `utils` — shared utility scripts
- `docs` — README, this file, project structure

## Examples

### ✅ Good

```
geo-sprint: feat: add playwright crawler for qianwen search results

Captures top-10 results for each query in keywords.txt.
Stores as JSON with platform/query/rank/title/url/snippet.

Refs: A-GEO_Sprint执行清单 §1.5
```

```
notes: docs: add embedding fundamentals

Covers text-embedding-3 vs BGE-large-zh selection criteria,
with minimal working example in Python.
```

```
geo-sprint: fix: handle empty search result pages

Some platforms return 200 with empty body — added retry + skip logic.
```

### ❌ Avoid

```
update stuff
WIP
fix bug
asdfasdf
```

## Frequency

- Commit **at least once per working session** (even if incomplete)
- Better: commit **per logical unit** (one feature, one note, one fix)
- Use `git add -p` for partial commits when needed

## Branching (later)

For now: stay on `main`.
When projects get bigger:
- `feat/<short-name>` for new features
- `fix/<short-name>` for bugs
- `docs/<short-name>` for docs

Merge with `--no-ff` to keep history.
