# Repolex Knowledge Graph of pydata/parallel

RDF knowledge graph data for [pydata/parallel](https://github.com/pydata/parallel), parsed by [repolex](https://repolex.ai).

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
rlex download pydata/parallel
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ebac6249c0bcb3faa0e21794450394ff71e44930
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ebac6249c0bcb3faa0e21794450394ff71e44930
│           └── chunk-001.nq.gz
├── blob
│   ├── 08b3e43a01f25fd32b89ef4edb411f87685120a8.nq.gz
│   ├── 12ddfa9565379dac193f6f9d3003edb4c6ee8cf3.nq.gz
│   ├── 2ebae94ebbcec6ea4b0b8011a3428b23d50c9204.nq.gz
│   ├── 7308138ea8367904b76196f314129a3b1aa82a76.nq.gz
│   ├── 783a9a7f06433720025e30e8e2d5c4d8cc4297a6.nq.gz
│   ├── 80f27716f0c5022e6c35b04e8bc7cb9c02b93d6c.nq.gz
│   ├── 89d4ea5a56b92bb20aaf5d60a3665cb2c34fa8b5.nq.gz
│   ├── 90b78083e54a9101a371ea5d1eb340e1b2c3d748.nq.gz
│   ├── 9bcdc1effa13c8ebbb4857304f204aa6ee03b000.nq.gz
│   ├── a6e21ba5621d78a1071af74417e900b689f31cc3.nq.gz
│   ├── a8759af5e861eaf28fd399af7cf8438849b4e185.nq.gz
│   ├── ce245f74210a14f65f5f6d586298b499ad02e6c8.nq.gz
│   ├── d28d5f1d0179902fa12c54d4fc981c9936047d5d.nq.gz
│   ├── d68dab0c6b9fbc28bdd38e5ad5a08ed3a219beb2.nq.gz
│   ├── db0c999ade222db7a848b58a451725d9d6b8a30f.nq.gz
│   ├── dd2390d1ffe66ef48dc1587c62fe84d441c3acf1.nq.gz
│   └── fb50d47ec0fcb482628a3dcb0f675c6d6dc9fded.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ebac6249c0bcb3faa0e21794450394ff71e44930.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 24 files
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

[pydata/parallel](https://github.com/pydata/parallel)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
