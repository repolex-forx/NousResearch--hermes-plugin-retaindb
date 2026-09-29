# Repolex Knowledge Graph of NousResearch/hermes-plugin-retaindb

RDF knowledge graph data for [NousResearch/hermes-plugin-retaindb](https://github.com/NousResearch/hermes-plugin-retaindb), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/hermes-plugin-retaindb
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5dde522dec252c12ad05861de8095d5a0cf7955f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 5dde522dec252c12ad05861de8095d5a0cf7955f.nq.gz
│   └── repolex
│       └── 5dde522dec252c12ad05861de8095d5a0cf7955f
│           └── chunk-001.nq.gz
├── blob
│   ├── 00f2d38d8063d0c6b219c0081e51888063b0c55e.nq.gz
│   ├── 0a2be38044a4f4abb5f3914c81c5cbec26600ecf.nq.gz
│   ├── 5ef080651823e8007d9c63ee3acd39258192286d.nq.gz
│   ├── 6cdba677950a9b900b76d0e7b0e40363784a43f4.nq.gz
│   ├── 75410e73319c72cd3e991a501c5455eb78f38375.nq.gz
│   ├── b5b236107c54c15ae938fa4238b70b2f301dbe1f.nq.gz
│   └── c14eee77bc44ecf11aeaef50cf8231e8cd7430ed.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 5dde522dec252c12ad05861de8095d5a0cf7955f.nq.gz
├── filetree
│   └── 5dde522dec252c12ad05861de8095d5a0cf7955f.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[NousResearch/hermes-plugin-retaindb](https://github.com/NousResearch/hermes-plugin-retaindb)

---
*Parsed on 2026-09-29 by [repolex](https://repolex.ai)*
