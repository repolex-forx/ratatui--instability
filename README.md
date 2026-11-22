# Repolex Knowledge Graph of ratatui/instability

RDF knowledge graph data for [ratatui/instability](https://github.com/ratatui/instability), parsed by [repolex](https://repolex.ai).

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
rlex download ratatui/instability
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2a4affca5ad534fc0826b4c556bdb2b851e4c886
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 2a4affca5ad534fc0826b4c556bdb2b851e4c886.nq.gz
│   └── repolex
│       └── 2a4affca5ad534fc0826b4c556bdb2b851e4c886
│           └── chunk-001.nq.gz
├── blob
│   ├── 1a2ea2e6a012c5d9b64ce67b42ddbd38e1f22e33.nq.gz
│   ├── 1de9877b55102fd6965982f5b76ac07f5f26a67f.nq.gz
│   ├── 2196ed6a881a1b7277a40b5913e5f4f014b4d9f3.nq.gz
│   ├── 220d5846c99103a4e5ac6ba034367828893184ad.nq.gz
│   ├── 4d4f0eecc2d1dc11bb4b0174ee8737caf93e00fc.nq.gz
│   ├── 4e4ab47b03885550b18862bbcd75378a58612e64.nq.gz
│   ├── 4fffb2f89cbd8f2169ce9914bd16bd43785bb368.nq.gz
│   ├── 6144b3975ed05f968aa8792100a08d519b1ac8f5.nq.gz
│   ├── 77af2e01d54b02646a004b6ae077b0ba093a579e.nq.gz
│   ├── 90a420d1a3e104dd4d0f42c2a22a61765f9ba6ba.nq.gz
│   ├── 95ab69579d391a2d6fd468bce2f4a33aeb5ca9f8.nq.gz
│   ├── a6cc03c3bbbed5f2b4105e278a9cdf542dc3d419.nq.gz
│   ├── b1b88eddb06850eb17890b3b5c82e601a538bcfd.nq.gz
│   ├── bbddfc6b2cf8043e64742d757b57dcccf43c0740.nq.gz
│   ├── c2537448046428da79127776757d229eae3924d6.nq.gz
│   ├── cfc1e1c011957b6116b0be3e5ed5e4a5dd5c1068.nq.gz
│   ├── de607731085719d3558437bd5c030107c2f11b45.nq.gz
│   ├── ecc8077bf2f35328d243471381108ec6290d8c00.nq.gz
│   └── f7533f421a7dacbe30728971e1a609ef4aa8f724.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 2a4affca5ad534fc0826b4c556bdb2b851e4c886.nq.gz
├── filetree
│   └── 2a4affca5ad534fc0826b4c556bdb2b851e4c886.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 29 files
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

[ratatui/instability](https://github.com/ratatui/instability)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
