# Repolex Knowledge Graph of samuelcolvin/cf-run-python

RDF knowledge graph data for [samuelcolvin/cf-run-python](https://github.com/samuelcolvin/cf-run-python), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/cf-run-python
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d7db0200c162801d50060c45c457eb65f7972ef7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d7db0200c162801d50060c45c457eb65f7972ef7
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e87a1d8ffad1e874c35156fbb43a402ecfe3ace.nq.gz
│   ├── 254fe77e001453ed66712db84f00f40ee5f0616c.nq.gz
│   ├── 3c1eb81e9da60f82902bfd931b94bff052431ef9.nq.gz
│   ├── 572b352f30e3b1568e0d6e291edec8803ed53fe4.nq.gz
│   ├── 7773e7f2317204e211d0f94005ee7dfcc35bc7b3.nq.gz
│   └── ec640f9d9130cf15efaf80ed14854b0d09a3439c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d7db0200c162801d50060c45c457eb65f7972ef7.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 12 files
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

[samuelcolvin/cf-run-python](https://github.com/samuelcolvin/cf-run-python)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
