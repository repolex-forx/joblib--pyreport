# Repolex Knowledge Graph of joblib/pyreport

RDF knowledge graph data for [joblib/pyreport](https://github.com/joblib/pyreport), parsed by [repolex](https://repolex.ai).

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
rlex download joblib/pyreport
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d91d19faa3c03f70a58234cde451eea7ca290d1b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d91d19faa3c03f70a58234cde451eea7ca290d1b
│           └── chunk-001.nq.gz
├── blob
│   ├── 0c6f5cbcf981a39bd1ecdace4ecdfe59d07a4cc9.nq.gz
│   ├── 0c70ce484f035c735012d6c39b248ff7db593227.nq.gz
│   ├── 255a5ff23e58d41b627656c49d5aa2e687ec355e.nq.gz
│   ├── 3e1ba69ac1e5a1fa4feab647cabef184c8886617.nq.gz
│   ├── 43315c75565a0699ac4f40499bff694b104e0ff7.nq.gz
│   ├── 5db4d3b6444844cb17587266ff4a1bc2bac22bb5.nq.gz
│   ├── 63bdfdf30e3a7e939ef4f636b9767f37d6c90d15.nq.gz
│   ├── 641a724bc0eba183d1c275a2f23aebc394d97829.nq.gz
│   ├── 65704bf9e8d348bec48671f177d32b4170be497e.nq.gz
│   ├── 82b4ea7bcdcd719074a4fa661f1c5b6416804f08.nq.gz
│   ├── 90ddd1088cfb94a0857825ffb34d87a1494df54f.nq.gz
│   ├── 9805ccdb8dae33233f40f722180c4fb9cd7ad632.nq.gz
│   ├── 9a3d5cd8eff49b3ed13266c1e6fd03243faf364f.nq.gz
│   ├── b25fb0afbf40b0cd078af4350070b22e47c58a73.nq.gz
│   ├── bd563d1172c9db7445b710369d9e613c752e884e.nq.gz
│   ├── c3a35ff2238619c40e441d7538774a08df74a9af.nq.gz
│   ├── cd68ea86c5bd65a72b15b82255e25e279b15529e.nq.gz
│   ├── d7d88212a0bd0e960da8ff697c294edab9dcd513.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f5d050a32917cbd76522e68b7d7d0cbe2bd823e8.nq.gz
│   └── fd99cf7cfccdc268bad5de6e4a517396b4250c0c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d91d19faa3c03f70a58234cde451eea7ca290d1b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[joblib/pyreport](https://github.com/joblib/pyreport)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
