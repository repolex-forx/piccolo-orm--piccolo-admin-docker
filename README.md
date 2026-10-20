# Repolex Knowledge Graph of piccolo-orm/piccolo-admin-docker

RDF knowledge graph data for [piccolo-orm/piccolo-admin-docker](https://github.com/piccolo-orm/piccolo-admin-docker), parsed by [repolex](https://repolex.ai).

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
rlex download piccolo-orm/piccolo-admin-docker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bd1b74b9c94444aadf162968fcd35c06c9ae4110
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bd1b74b9c94444aadf162968fcd35c06c9ae4110
│           └── chunk-001.nq.gz
├── blob
│   ├── 068800807fdd30e9e69ffa56641fb150bd2034bc.nq.gz
│   ├── 1c31d45b8ea145f4f3117a2171ba54012aa0f9f3.nq.gz
│   ├── 1e965f57d1c3ec598bb85cae7fb6dba4e2e17cba.nq.gz
│   ├── 2f42ae34ee64945d0193682043c9f394d8d08bf2.nq.gz
│   ├── 2f949b8c2e2e4898fb6ae6d4029695d007892a4d.nq.gz
│   ├── 3acfde1c1fff78831b9f4047d504302924550f3b.nq.gz
│   ├── 4e8fafb5d1c27c7f94bed3eec81045394ce43671.nq.gz
│   ├── 78e0e79ed4d21848bb82e4fea038d59c9ae2d7be.nq.gz
│   ├── a92e75f0060ec9779f53c998406c4d0302ec2802.nq.gz
│   ├── b8085407e49710665c02078618386e23b639def0.nq.gz
│   ├── bb8708ab9e48580c82886b569cf7cb5e2f7a428b.nq.gz
│   ├── d367308b9f4610297ead5d387e4667ea94433d2a.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bd1b74b9c94444aadf162968fcd35c06c9ae4110.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[piccolo-orm/piccolo-admin-docker](https://github.com/piccolo-orm/piccolo-admin-docker)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
