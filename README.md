# Repolex Knowledge Graph of kennethreitz/omnijson

RDF knowledge graph data for [kennethreitz/omnijson](https://github.com/kennethreitz/omnijson), parsed by [repolex](https://repolex.ai).

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
rlex download kennethreitz/omnijson
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a5890a51a59ad76f78a61f5bf91fa86b784cf694
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a5890a51a59ad76f78a61f5bf91fa86b784cf694
│           └── chunk-001.nq.gz
├── blob
│   ├── 0052fc7a25a63d12fa597683493acd13362f6904.nq.gz
│   ├── 1afc2de0413619b746723b3ee98e1a8df6c8cf50.nq.gz
│   ├── 210b957a9da4def89b6dbe8bd00aa0adae421902.nq.gz
│   ├── 3e36e567f299a83e7710f9b263358f2ff93e603f.nq.gz
│   ├── 4c7a2bc239d42cb40f2b90fcbb2010aac290a60a.nq.gz
│   ├── 764ee3c18b0846200639ef1621760bc589c222c0.nq.gz
│   ├── 80b40a94d34633a50b43a6def866770e7fb84542.nq.gz
│   ├── 87ad8882482ca02970df711f4aa1039bece45cb9.nq.gz
│   ├── 8cb051802be3d1a85b619687ea861f8d05517370.nq.gz
│   ├── 9eaaca38568ff000dbcc4e8e2814172be11996dc.nq.gz
│   ├── c10c328fc86be4de14a9776afed823cdca133cbb.nq.gz
│   ├── dc6b0ff4110c9a92bce57bac2216b46e5f4ac7cc.nq.gz
│   ├── e11aef497eae23639870ff4ef7d87771d1e3c15b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f1269f3f0c3fc3d714ec3bb819489073ff5d7043.nq.gz
│   ├── fcaa30c0e16e22998ae2b647cd1cb15622de2288.nq.gz
│   └── fd0ff958ca903bfb09016484a0e6b3cc2835ea27.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a5890a51a59ad76f78a61f5bf91fa86b784cf694.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[kennethreitz/omnijson](https://github.com/kennethreitz/omnijson)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
