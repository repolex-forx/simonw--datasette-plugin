# Repolex Knowledge Graph of simonw/datasette-plugin

RDF knowledge graph data for [simonw/datasette-plugin](https://github.com/simonw/datasette-plugin), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-plugin
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ee9f1f1bb15c6b8709bb31a7d49cf5fc7d3ee24d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ee9f1f1bb15c6b8709bb31a7d49cf5fc7d3ee24d
│           └── chunk-001.nq.gz
├── blob
│   ├── 02b32735c73a90d6f3c9321f4129f0a09a03f61b.nq.gz
│   ├── 15961e1a847c627f9a1c47f2031eba1ddcf896f5.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2e45dab216a14392967d22b9cb0d1585d7e52d2c.nq.gz
│   ├── 3155f072e1cb22cc57e296d53d7ebbebcac03c00.nq.gz
│   ├── 35be30dff158330768753d988296bb824c40aba7.nq.gz
│   ├── 399cf9f184d5ffa0887f9ed1f4125d6e83cad4c4.nq.gz
│   ├── 57f31473296d8557b1630855002c9f47d210b6d8.nq.gz
│   ├── 5be11905be4553a3a1fe88ad1502de120aa4530f.nq.gz
│   ├── 62bd1075fe34616f626d29399d729516e8dde742.nq.gz
│   ├── bc78c1c4905bfe9c233a3c0dee9ad50a2a59ac8c.nq.gz
│   ├── d120c29d827a30bd065b25a9f118231f6ce78186.nq.gz
│   ├── d84880d1956234d57e3af0d1c63c6aa58e89350c.nq.gz
│   ├── db00e6fb015e0a34f5c5b069360a9a7bda8ba1ab.nq.gz
│   └── eb22e74eaaaf0edc4aa2c0f8900a55750d1660f9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ee9f1f1bb15c6b8709bb31a7d49cf5fc7d3ee24d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[simonw/datasette-plugin](https://github.com/simonw/datasette-plugin)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
