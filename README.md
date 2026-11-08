# Repolex Knowledge Graph of UKPLab/acl2020-empowering-active-learning

RDF knowledge graph data for [UKPLab/acl2020-empowering-active-learning](https://github.com/UKPLab/acl2020-empowering-active-learning), parsed by [repolex](https://repolex.ai).

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
rlex download UKPLab/acl2020-empowering-active-learning
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 13159f2a7ce10aa78d8fea84e321f63bbe903d39
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 13159f2a7ce10aa78d8fea84e321f63bbe903d39
│           └── chunk-001.nq.gz
├── blob
│   ├── 15225344a09266e70197c827a70947e4e8f4356d.nq.gz
│   ├── 295ed272211ff7904a20a3810776e68dc54db493.nq.gz
│   ├── 5a427c5748bc3e3379f052ad3bda550ce55f898f.nq.gz
│   ├── 651c95bdc5e724d1da0d2a0596b03642cb1a97b9.nq.gz
│   ├── 88b187ea69a60511fe17866b4edb4fa3dfff868e.nq.gz
│   ├── a85c934cfe4d86347363a932ae640c9f0d0b3ba7.nq.gz
│   ├── ae4b87a1adb696585e328aa5cc2fa7fa5a5db43f.nq.gz
│   ├── d335aa2aa4d4a044fed229c889b21f56828b5dd1.nq.gz
│   ├── d9b6c220e057989f5b41cc0df07571e6e3ef78e7.nq.gz
│   └── e2cc00ef590bf989ae8c196db042c4dc2f0df42b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 13159f2a7ce10aa78d8fea84e321f63bbe903d39.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[UKPLab/acl2020-empowering-active-learning](https://github.com/UKPLab/acl2020-empowering-active-learning)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
