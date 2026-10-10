# Repolex Knowledge Graph of tiangolo/latest-changes

RDF knowledge graph data for [tiangolo/latest-changes](https://github.com/tiangolo/latest-changes), parsed by [repolex](https://repolex.ai).

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
rlex download tiangolo/latest-changes
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a7500b7359fdef831b5c192e9c86865e4e464574
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a7500b7359fdef831b5c192e9c86865e4e464574
│           └── chunk-001.nq.gz
├── blob
│   ├── 05bf42391580e4651027b22a8aca65916aa6dae7.nq.gz
│   ├── 2794043aa44b74930076da51ec2d7b0b4cfcbe92.nq.gz
│   ├── 2e7facd7bfe0f68bd066aaa66c46de3f2432e804.nq.gz
│   ├── 2f5ed143798bf5820ae67d8233ccf389e60467ce.nq.gz
│   ├── 57cf94c45e624dfc04810c7fa73223d4337ef323.nq.gz
│   ├── 5d6a8109e6ce6ef4587c5fb02bb9d621aa3fa09b.nq.gz
│   ├── 604d34d960275a872aeec655f24d364017ec58a6.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 7766e079d0921630d7e4c4431bd11d4d2b862138.nq.gz
│   ├── 79e4fb8b5a3220d8625061aaee94f3e17d468bde.nq.gz
│   ├── 9597c2c5b58db200930d92b03c910bcb878f319b.nq.gz
│   ├── 9a2191fca28591ed165f38c21779b5931187a355.nq.gz
│   ├── a52e88bcc3c9994d8d075efea9a9f770a8dcdd81.nq.gz
│   ├── a9b357a80845283c3a0d21094715a7c701d1b111.nq.gz
│   ├── ab691199d2e4f6fb95883a26c9406c4a58d7e564.nq.gz
│   ├── b0348c75aea6ac2eca4735d13102c647ae6010fd.nq.gz
│   ├── b05a8166a1bad2d6bc57a1ab232bd6705df88909.nq.gz
│   ├── cf0df19ddf7c40a957f8b6538963fa99158edc39.nq.gz
│   ├── d30386da51824a9cf582bdc25cc692a96d1a3521.nq.gz
│   ├── d535dc8c53b768076670f0c4408673cbeaeef7b1.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e727befabca58f0fb329a4d2a21eb3a3c449eca4.nq.gz
│   └── f095f61be349f64d225ad04653345378658baa2e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a7500b7359fdef831b5c192e9c86865e4e464574.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 31 files
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

[tiangolo/latest-changes](https://github.com/tiangolo/latest-changes)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
