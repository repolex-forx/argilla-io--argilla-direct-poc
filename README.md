# Repolex Knowledge Graph of argilla-io/argilla-direct-poc

RDF knowledge graph data for [argilla-io/argilla-direct-poc](https://github.com/argilla-io/argilla-direct-poc), parsed by [repolex](https://repolex.ai).

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
rlex download argilla-io/argilla-direct-poc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 72c97abc31a308e2fc53dc03cdb5a35ab84281c0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 72c97abc31a308e2fc53dc03cdb5a35ab84281c0
│           └── chunk-001.nq.gz
├── blob
│   ├── 019982a6cf30a77e481ff850b64998516cea887c.nq.gz
│   ├── 39e7ae7fd0fdd2d8e5bc370225bb1f3eb8648ac8.nq.gz
│   ├── 5e355d2ef599ecfd0388a937222c4e2f7bee6f01.nq.gz
│   ├── 75c07357ae894e21570a9983082923f7627b4b0b.nq.gz
│   ├── b7d07210606db05e1c86e750621dd2921df0cbdd.nq.gz
│   ├── b9a2bbb5a0494fb1b4489344e13e210d8dc02de7.nq.gz
│   ├── e379d4f0b03a2982f974e9278b9a5733704cb760.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fffb055313ef9fd3b3ff2b2b69c53e1fc1fff83b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 72c97abc31a308e2fc53dc03cdb5a35ab84281c0.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[argilla-io/argilla-direct-poc](https://github.com/argilla-io/argilla-direct-poc)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
