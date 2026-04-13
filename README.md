# Repolex Knowledge Graph of wolever/parameterized

RDF knowledge graph data for [wolever/parameterized](https://github.com/wolever/parameterized), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download wolever/parameterized
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 80cbc497448eef363880bc814bc02684c2d2e70d
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 80cbc497448eef363880bc814bc02684c2d2e70d.nq.gz
│   └── repolex
│       └── 80cbc497448eef363880bc814bc02684c2d2e70d
│           └── chunk-001.nq.gz
├── blob
│   ├── 1139fc4ea2af090cd7b94009d2e6eebc50243587.nq.gz
│   ├── 216279017da6f737f384fef779bcdee62e19af77.nq.gz
│   ├── 25ff0f19084c7572c2eca1c1168f0cc4d1032af6.nq.gz
│   ├── 4da8c05f16518d9e086cd94dd0055b304c32cefa.nq.gz
│   ├── 55b43e3f58f18ca76ba6e92ec08a5a65980d1adb.nq.gz
│   ├── 5dbb9176075fd35f3f32194edf75706835213791.nq.gz
│   ├── 5f5224b243fd7fffd460529f0757943ec235b4d9.nq.gz
│   ├── 67a3ccfd05fa9812a848437527ed37db911a610f.nq.gz
│   ├── 864bb9ed0bf97e34e942989fb1dab2bee1ffdb03.nq.gz
│   ├── 8b00ddc107476dc80b12b714040d7d942e46eb87.nq.gz
│   ├── 969a157459879e678ac09c3c27741dfc3fb51908.nq.gz
│   ├── d0531b989379eb08bcd01bd4bf0cfa007346397b.nq.gz
│   ├── d2385e49a1c40f26d1e9c4c1d2bfce41ed09dbcd.nq.gz
│   ├── e58a36e52d82b87dd090618a141d8f7a94ba492a.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f98d86544f64e1f87479bba0d6d482e6e8786380.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 80cbc497448eef363880bc814bc02684c2d2e70d.nq.gz
├── filetree
│   └── 80cbc497448eef363880bc814bc02684c2d2e70d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 26 files
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

## Source repository

[wolever/parameterized](https://github.com/wolever/parameterized)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
