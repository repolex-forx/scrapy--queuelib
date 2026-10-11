# Repolex Knowledge Graph of scrapy/queuelib

RDF knowledge graph data for [scrapy/queuelib](https://github.com/scrapy/queuelib), parsed by [repolex](https://repolex.ai).

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
rlex download scrapy/queuelib
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 885ef61c6ad9b61682329074f539cbb8c262a580
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 885ef61c6ad9b61682329074f539cbb8c262a580
│           └── chunk-001.nq.gz
├── blob
│   ├── 121bab9254358b8f9e07d46dbd1e961a77243078.nq.gz
│   ├── 213dfe299067ae1c4711c344390099adfad132d6.nq.gz
│   ├── 219a385c05f54e587ca4e494ae8a9a4a892146fb.nq.gz
│   ├── 30000af39d04e6ad6502abab5d30acf7c4ae38f0.nq.gz
│   ├── 3c8e6ffb2b3b2cfee22784d4e8794d176a43100b.nq.gz
│   ├── 414d4653c2b7a2e73318fa70c79442496eaa1b4f.nq.gz
│   ├── 5f7c4b30e1e316197e97e5c26b8d2490b504c944.nq.gz
│   ├── 623d48cfa6b6f2ba551dde2435254ed5a1b63862.nq.gz
│   ├── 63baa703476fd9697a6a172628be516e367c5450.nq.gz
│   ├── 73be79e29b4de3dd618a12977ee52810ff2cb084.nq.gz
│   ├── 796a7d09482f10573cbc30c5b50232711dde61ad.nq.gz
│   ├── 7c136658a2f5079e25958d13e565c4b8f44ad544.nq.gz
│   ├── 7e45c9eea12dab5acf7e175ea684504b8321c710.nq.gz
│   ├── 9dcff6f8cf1d35b974c08e0686e6459f3b7c30ee.nq.gz
│   ├── a4f0e759afc84843376b43f04fee24f0bdb3c12a.nq.gz
│   ├── b9a71cc107698e2dd35d1b3826e290b07c2c0967.nq.gz
│   ├── bc75750005c5a98498563f1ab9a13440d48279c9.nq.gz
│   ├── d8aaf130955a883d901effa98f0d1acd0b595258.nq.gz
│   ├── dc1690869dcc5b31ceb7c3cad6f0fbee04de9bdf.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── eabd8a98a48deb257336ecf20565c18bb78475a8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 885ef61c6ad9b61682329074f539cbb8c262a580.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[scrapy/queuelib](https://github.com/scrapy/queuelib)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
