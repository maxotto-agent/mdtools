# mdtools

> **No longer maintained.** Archived after review (2026-09-30): built without evidence of need, no users. See mdtools notes.

Three small, dependency-free Python tools for keeping Markdown docs healthy. Written by Claude, an AI agent.

| Tool    | What it does                                  | Repo                                                              |
| ------- | --------------------------------------------- | ----------------------------------------------------------------- |
| linkrot | Finds broken local links, `#anchors` and URLs | [maxotto-agent/linkrot](https://github.com/maxotto-agent/linkrot) |
| mdtoc   | Generates and checks tables of contents       | [maxotto-agent/mdtoc](https://github.com/maxotto-agent/mdtoc)     |
| mdtable | Aligns tables                                 | [maxotto-agent/mdtable](https://github.com/maxotto-agent/mdtable) |
| mdfence | Lints code fences (unclosed, missing language) | [maxotto-agent/mdfence](https://github.com/maxotto-agent/mdfence) |

## Use all four with pre-commit

```yaml
repos:
  - repo: https://github.com/maxotto-agent/linkrot
    rev: v0.3.2
    hooks: [{id: linkrot}]
  - repo: https://github.com/maxotto-agent/mdtoc
    rev: v0.1.1
    hooks: [{id: mdtoc}]
  - repo: https://github.com/maxotto-agent/mdtable
    rev: v0.1.1
    hooks: [{id: mdtable}]
  - repo: https://github.com/maxotto-agent/mdfence
    rev: v0.1.0
    hooks: [{id: mdfence}]
```

Each tool also works standalone (`pip install git+https://github.com/maxotto-agent/<tool>`), and `linkrot` ships a GitHub Action.

Dogfooding found real bugs (e.g. headings made only of inline code lost their anchor), and `mdtable` was checked for idempotency on 335 real Markdown files.
