# Repolex Knowledge Graph of astropy/astropy-mentoring

RDF knowledge graph data for [astropy/astropy-mentoring](https://github.com/astropy/astropy-mentoring), parsed by [repolex](https://repolex.ai).

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
rlex download astropy/astropy-mentoring
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── beb1965abd4b9d01423fe382e420e428c38939d0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── beb1965abd4b9d01423fe382e420e428c38939d0
│           └── chunk-001.nq.gz
├── blob
│   ├── 153be5e2f6f996741b53558d8bc7825ec091699c.nq.gz
│   ├── 22f3c215ad6088c2ac6571c962cd468c6398d72b.nq.gz
│   ├── 4d2dac35014a4e33032ff4672b286f5fe15384c4.nq.gz
│   ├── 64cf918436c2e441e011a9060497e7f3280b4ba2.nq.gz
│   ├── 7a06e05e5c8940fa63aa6f58864c2a9e003162ae.nq.gz
│   ├── 87d6a6e3c3f6d1317e528b60cf15c75aca77d276.nq.gz
│   ├── 89df208238c387d0f70a8c7cdf222b14f0eabbe5.nq.gz
│   ├── 9d33a896f3736a80bad6355a925ac6e6d58fb0f2.nq.gz
│   ├── bab6b9a98334edf81084c2b031cf991fa08c736b.nq.gz
│   ├── bfd7c8853731bf64fc55dd7409b154ac336373ec.nq.gz
│   ├── d4bb2cbb9eddb1bb1b4f366623044af8e4830919.nq.gz
│   ├── e35d8850c9688b1ce82711694692cc574a799396.nq.gz
│   ├── e36aec32cb127c9d6251cee3347cc78dbb2d75e9.nq.gz
│   └── f57ca0d6c992f9315f609a4487b64e8359c72e10.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── beb1965abd4b9d01423fe382e420e428c38939d0.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[astropy/astropy-mentoring](https://github.com/astropy/astropy-mentoring)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
