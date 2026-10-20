# Repolex Knowledge Graph of klen/pylama_pylint

RDF knowledge graph data for [klen/pylama_pylint](https://github.com/klen/pylama_pylint), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download klen/pylama_pylint
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8359b449f0e47e6e3e9378cd3e77cf29df49418e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8359b449f0e47e6e3e9378cd3e77cf29df49418e
│           └── chunk-001.nq.gz
├── blob
│   ├── 02667cc7c9a6ec44db15cfacafbc07c364c05af4.nq.gz
│   ├── 033f16485cf71664c0760c6d75c7adbdd7d736e5.nq.gz
│   ├── 35afcf2874201aa8acc21adbad4612dd2327c4ff.nq.gz
│   ├── 3b8d173b8fba1b7938a0add1685a54e3d4377317.nq.gz
│   ├── 42a65ccf9ee61e65c708cd8805e08d0be13dcf0c.nq.gz
│   ├── 50c0c3459cc99487bb9e4b1f388afafc40f755fe.nq.gz
│   ├── 532f56c85463cb5f1e8ac04921f5e086fe794ffa.nq.gz
│   ├── 53a8ef088cd4df6dcb4265e6af6ebbc3b42d8c54.nq.gz
│   ├── 6ec8fb0b8efbe4d96317334909b0a402fc33aff8.nq.gz
│   ├── 88003c5185842327b13110f4ac1c7e803233223e.nq.gz
│   ├── 8951ea8e619d97d651aa55e8dee549b29b31a746.nq.gz
│   ├── 9ad8f49f115e1a5af252b659fb9a26ebabe1a0d4.nq.gz
│   ├── a45f5e1d1bd349ede5af0ff19d3e81d57610037a.nq.gz
│   ├── ac2030c4a3227d2627351c557395502e95b441e5.nq.gz
│   ├── c4a39179a1317c0059d188a90e134117279d5e85.nq.gz
│   ├── d450b674ca83d9b71b818c8188466e9472d1e1d4.nq.gz
│   ├── dbe844941bf3581d0dd94b3f7cbd328b09b7c9f3.nq.gz
│   ├── e6360141a80f65f42994af70b828a54eed76136b.nq.gz
│   ├── e7fae4c46766f802fde16d18aa6b65b9b700834b.nq.gz
│   └── ea49009655244e5bf791697a512b63f772495832.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8359b449f0e47e6e3e9378cd3e77cf29df49418e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[klen/pylama_pylint](https://github.com/klen/pylama_pylint)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
