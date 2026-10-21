# Repolex Knowledge Graph of bokeh/conduct.bokeh.org

RDF knowledge graph data for [bokeh/conduct.bokeh.org](https://github.com/bokeh/conduct.bokeh.org), parsed by [repolex](https://repolex.ai).

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
rlex download bokeh/conduct.bokeh.org
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 23c805e46af0417ad512cdc79582c9e6f12f4f48
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 23c805e46af0417ad512cdc79582c9e6f12f4f48
│           └── chunk-001.nq.gz
├── blob
│   ├── 2e53b77331dde4b521bc2c9128391148be7cb780.nq.gz
│   ├── 4cfe860c3190db3211a05321b246430bc38006c3.nq.gz
│   └── a528fa0b1cf449458fd1d862bc3ab6c2e4e2a09f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 23c805e46af0417ad512cdc79582c9e6f12f4f48.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 9 files
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

[bokeh/conduct.bokeh.org](https://github.com/bokeh/conduct.bokeh.org)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
