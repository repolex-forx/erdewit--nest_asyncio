# Repolex Knowledge Graph of erdewit/nest_asyncio

RDF knowledge graph data for [erdewit/nest_asyncio](https://github.com/erdewit/nest_asyncio), parsed by [repolex](https://repolex.ai).

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
lexq download erdewit/nest_asyncio
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 19f396f9396bfd34b1b0caeb9b4c631ee3d7eb21
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 19f396f9396bfd34b1b0caeb9b4c631ee3d7eb21.nq.gz
│   └── repolex
│       └── 19f396f9396bfd34b1b0caeb9b4c631ee3d7eb21
│           └── chunk-001.nq.gz
├── blob
│   ├── 065cc87368b36ede418c888a28920622944c4ec8.nq.gz
│   ├── 076dbfeea267828ad2086f94b14bf4ee667d2b33.nq.gz
│   ├── 1cb5c253fa0658a0adea3516f6463904396cf573.nq.gz
│   ├── 26e08e48e8f82869ef1dec35972ee25826efecfb.nq.gz
│   ├── 5f713a454862488e41aeb5a03abf55e51a3d2a84.nq.gz
│   ├── a9db5a536f314d9b7faa94f99d9fcbd8a07c7412.nq.gz
│   ├── ac450e30899281e84e3ca524a09a57b612b76a80.nq.gz
│   ├── b19a8d44a9886bdb0839b433d9fca5f47d957621.nq.gz
│   ├── d74bb79213bfffc5352160f8fedc4884bbd92a49.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e920253bfa5afeb6c5a551553fdae1847ddff262.nq.gz
│   ├── f5b4001b0a54dc255103e9d70a51881db058fc88.nq.gz
│   └── ff9fbedb49cc271890582f0c6f8c454acbd9d7d2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 19f396f9396bfd34b1b0caeb9b4c631ee3d7eb21.nq.gz
├── filetree
│   └── 19f396f9396bfd34b1b0caeb9b4c631ee3d7eb21.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
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

[erdewit/nest_asyncio](https://github.com/erdewit/nest_asyncio)

---
*Parsed on 2026-04-14 by [repolex](https://repolex.ai)*
