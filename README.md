# Repolex Knowledge Graph of sphinx-contrib/redoc

RDF knowledge graph data for [sphinx-contrib/redoc](https://github.com/sphinx-contrib/redoc), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/redoc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5b9906badea7cd6cac369aa91f0e6ca288d71fff
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5b9906badea7cd6cac369aa91f0e6ca288d71fff
│           └── chunk-001.nq.gz
├── blob
│   ├── 1c177b7a4507485ee444b9a0e432428b70c30aec.nq.gz
│   ├── 276708bcf9b7c74a79106dcaac305067460fa5c4.nq.gz
│   ├── 43ae4518c67c4348048bce9737c1e488b489c3f6.nq.gz
│   ├── 4837bb1b2e4a5fa6ce51e58bb8f094499d466a36.nq.gz
│   ├── 4b631fa16515530601d595c752d98a35c52b21ee.nq.gz
│   ├── 5ae493c836a5f5576f633d868d49213878cf4ddd.nq.gz
│   ├── 6e1c194745603db504eb572623383f6acf4ec32b.nq.gz
│   ├── 7f14f9578d9251a75f7d930ce566d4ebc50697be.nq.gz
│   ├── 9dee192398d5fb56b3cb0224b0d8fa7000878ed4.nq.gz
│   ├── c45d0481c6abda5c2159cc7014777626a75b0e3f.nq.gz
│   ├── c9843c9bc668566741c5722f971730aa2eea5eda.nq.gz
│   ├── d5d3dd099970b382d811bdf7c66a44a29edbea4c.nq.gz
│   ├── d7ab500d850201b22c062f3f9565ed07b078a9dc.nq.gz
│   ├── d91575a5bbe6b80bce2ccc4cf6915ccd2bf2adce.nq.gz
│   ├── e6788e1adf3ccc5f7f8ed54e62e1ac5e8260ba03.nq.gz
│   ├── f05540e5117f9c3941cffc85fe4cffcd9075ddf0.nq.gz
│   ├── f1e2315f93c46cdc0baa47b6a9a36c66cdf135a9.nq.gz
│   └── fd5fe5c8bea31e8e688eaee6ae9a7a5f86988255.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5b9906badea7cd6cac369aa91f0e6ca288d71fff.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 26 files
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

[sphinx-contrib/redoc](https://github.com/sphinx-contrib/redoc)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
