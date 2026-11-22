# Repolex Knowledge Graph of Amanieu/thread_local-rs

RDF knowledge graph data for [Amanieu/thread_local-rs](https://github.com/Amanieu/thread_local-rs), parsed by [repolex](https://repolex.ai).

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
rlex download Amanieu/thread_local-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4b7cc0f30b81b768fafc4b0ef4d541bfc94a0433
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4b7cc0f30b81b768fafc4b0ef4d541bfc94a0433.nq.gz
│   └── repolex
│       └── 4b7cc0f30b81b768fafc4b0ef4d541bfc94a0433
│           └── chunk-001.nq.gz
├── blob
│   ├── 16f6516de709e6b219235e1d58841dfcdbd55b22.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 40b8817a47beba464cd86e3f81260cd41b5e70dd.nq.gz
│   ├── 84b23deaa6212f6d9a40dcdb7a56315ef62763c4.nq.gz
│   ├── 867c0abbdbd5cb3d7435556f22b1c4c75ad78801.nq.gz
│   ├── 91b623374a0f63a80ad5ceab04502b6b6d9d4610.nq.gz
│   ├── 9a8f610d905d65ee6d7f6399596e69aa118f1579.nq.gz
│   ├── c6ae68606be997967bb1fa46061bc324466b5808.nq.gz
│   ├── c7440b79dcac2bfe460cada24c9479e41182f040.nq.gz
│   ├── d055f9b57dc7f0a4187a8feba4830a7a75162f4c.nq.gz
│   ├── d97d1730b70b70b1785ebb4d7b188fc1b600f987.nq.gz
│   ├── db4d831ac2314c540cfbc1d64acfec6d1038c596.nq.gz
│   ├── dd4716d87c89736859d6fb489a07a1a94736bb5d.nq.gz
│   └── eb5a316cbd195d26e3f768c7dd8e1b47299e17f8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 4b7cc0f30b81b768fafc4b0ef4d541bfc94a0433.nq.gz
├── filetree
│   └── 4b7cc0f30b81b768fafc4b0ef4d541bfc94a0433.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 24 files
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

[Amanieu/thread_local-rs](https://github.com/Amanieu/thread_local-rs)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
