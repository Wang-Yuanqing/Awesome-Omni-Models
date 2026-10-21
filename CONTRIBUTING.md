# Contributing

Add papers on temporal understanding, memory, cross-modal synchronization, online reasoning and interaction, or benchmarks. Related text-agent memory, speech systems, and offline diagnostics belong in the labeled supporting tables.

1. Link the primary paper and verify its name, identifier, and **first preprint month** (YYYY.MM).
2. Choose the best-fitting table and insert the entry in newest-first order.
3. Use a recognizable method name and one short sentence explaining its contribution.
4. Link official code, data, or project pages; label each resource accurately.
5. Keep claims tied to demonstrated capabilities. Streaming output alone does not establish streaming input or full-duplex interaction; label offline and supporting work clearly.
6. Explain the addition or correction in the pull request and link the supporting source.

Use four columns, with no modality abbreviations:

```markdown
| YYYY.MM | [**Method name**](https://arxiv.org/abs/ID) | One concise contribution. | [Code](https://github.com/OWNER/REPO) |
```

For benchmarks, describe what the evaluation tests. Use `—` when no official resource is available. Avoid duplicate entries unless a paper introduces both a method and a benchmark.

Before submitting, check dates, links, table formatting, and ordering. Update the README's paper count and update badge when needed; count distinct papers rather than table rows.

Keep [English](README.md) and [简体中文](README.zh-CN.md) entries in sync when adding or correcting a paper.
