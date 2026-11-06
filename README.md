# Repolex Knowledge Graph of sphinx-contrib/autofile

RDF knowledge graph data for [sphinx-contrib/autofile](https://github.com/sphinx-contrib/autofile), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/autofile
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bf04c27133e6f738c8b9d50c73d9186b95134596
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bf04c27133e6f738c8b9d50c73d9186b95134596
│           └── chunk-001.nq.gz
├── blob
│   ├── 03969d46c77d7a97615f3504dd366ac292fb9ac2.nq.gz
│   ├── 1a5d436a26705eb778cb99b1e78237056391b8af.nq.gz
│   ├── 1da65476d7a0b956d8267c046b636fc9a45d1416.nq.gz
│   ├── 209d62fd65c87c0afd187808464af4a346d40d2c.nq.gz
│   ├── 3267e4dcb89ba66e90050a566b3698e93467eadb.nq.gz
│   ├── 4b1639fadbe5345ad96120e624d391816e52ef39.nq.gz
│   ├── 4cd3417ae7577b6e268c8a0f90eadf3b07e8691f.nq.gz
│   ├── 54082ccd5dea414080bd6c6fc5378d8600a9a216.nq.gz
│   ├── 6c837615295dd7dfb19724c0c46859eec4888a46.nq.gz
│   ├── 7658cd60562871ffeb629e72b9a3f3a412ce70b1.nq.gz
│   ├── 7dd10c9ffb2894d7873e06630fa2cf7c4a8d9e58.nq.gz
│   ├── 7f3619bd5f9f7a09f973b176558c85b342c0750b.nq.gz
│   ├── 89589ad827db1547523e3422ae82ea4237ae3ee3.nq.gz
│   ├── 89a3f3213ac6c9438d70dec80ec4627ee5dbd078.nq.gz
│   ├── 958666f1195a9fd5fc2b1fd405c85b4ee9e7b213.nq.gz
│   ├── 9e3565b59197c63d415f3800a5642b5dcf55dbf5.nq.gz
│   ├── a24ecdd1dc9fa6d83c1c739b72e55c4f4f78a71b.nq.gz
│   ├── ae4800099b7b0582bf30ff9a4f5efc90e1c9dab5.nq.gz
│   ├── b39c4f8374a749c8580eb189e1e649532c7e4c61.nq.gz
│   ├── b92bc38b04c1b0f0350720c0c52adf6a7cad2acd.nq.gz
│   ├── c42eb772f510b4ee8bd3df978017478afa75daad.nq.gz
│   ├── d280a7d6d269a87c975d0351e52bfed0270b18f2.nq.gz
│   ├── deb6973c309aac7e49128e0df5fb936333056333.nq.gz
│   ├── e3a21f400791009ab45ef6b1ddbaa9e474c0684e.nq.gz
│   ├── e525ed9a265af771c02411a7451623f872749003.nq.gz
│   └── f288702d2fa16d3cdf0035b15a9fcbc552cd88e7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bf04c27133e6f738c8b9d50c73d9186b95134596.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 33 files
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

[sphinx-contrib/autofile](https://github.com/sphinx-contrib/autofile)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
