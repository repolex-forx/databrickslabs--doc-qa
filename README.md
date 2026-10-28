# Repolex Knowledge Graph of databrickslabs/doc-qa

RDF knowledge graph data for [databrickslabs/doc-qa](https://github.com/databrickslabs/doc-qa), parsed by [repolex](https://repolex.ai).

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
rlex download databrickslabs/doc-qa
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9580a59f8044c289dffddabbce7ec01971b938d2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9580a59f8044c289dffddabbce7ec01971b938d2
│           └── chunk-001.nq.gz
├── blob
│   ├── 173590998a551d455fdae15cf1e190c731082847.nq.gz
│   ├── 18f92354bd1904e2fbabca06acac1e501cdd3d46.nq.gz
│   ├── 1c0dd0800b9d984063cf803fbc63862ea24db827.nq.gz
│   ├── 2533e029c0910ca27229d68f1032341aa3acf2b2.nq.gz
│   ├── 2583cceaf5947304be949b76c5602e2a55662dad.nq.gz
│   ├── 279fd74d28dbf1c01555a7c054c487acbbb48283.nq.gz
│   ├── 31407ae34ccb72b033bb18f3a496debb29d2ece7.nq.gz
│   ├── 3fd126d6252b3c2badc3d2ca1653e1dd1038b1ef.nq.gz
│   ├── 41931450ee7a407abb68263a6a1a73d13fe41137.nq.gz
│   ├── 492def9631c8fce1c633d2ae0430551f822c61e8.nq.gz
│   ├── 4f3758aad79d13f52e2f5eed7425a0b988b47a97.nq.gz
│   ├── 541ed50c9967e49b9c10fe107260ba94c5107166.nq.gz
│   ├── 546ffc5e9c2a5d02bb5ae640072b4e28bf087dc7.nq.gz
│   ├── 5d72b27949a0277a64a55a167d7309c6175d9cd3.nq.gz
│   ├── 5ff39eb9f9ab2a36b981c5f1884b2e35b784a2f7.nq.gz
│   ├── 6842129bb7c89c79ac765649e494a45068ab669c.nq.gz
│   ├── 77b944b8d235b7838e97f405d38da67e94695674.nq.gz
│   ├── 87752f4712a95b24765692089b67fcbbf04ece66.nq.gz
│   ├── 919a7aab67e45ff69c1419180becc5adaa70bc54.nq.gz
│   ├── 9e2f702d92319dfc7f0b694a286a06355056f725.nq.gz
│   ├── 9fa1c492c15328f7685d2b6d56f811954b7ceefc.nq.gz
│   ├── a9ffd0d07bf88dac130f9f5a7ae80f189243649c.nq.gz
│   ├── adb2721366aa0e58500ba708343194d08208ea95.nq.gz
│   ├── afc90cc7e0cb0be239abc0889f0860c15beea014.nq.gz
│   ├── ba1c6b80acf7f6ff91ba28f6e9278986f1c24301.nq.gz
│   ├── bce81ffab99e6f804abe9171c551db26528fc8ec.nq.gz
│   ├── cbc50b39ca3654e2516dd210f76d50a0989b1fc5.nq.gz
│   ├── cd468ce2ef28909918b622c47ec877fff25154b2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ec6bdc76a358260c8c7ed30572f42445e319700d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9580a59f8044c289dffddabbce7ec01971b938d2.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 37 files
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

[databrickslabs/doc-qa](https://github.com/databrickslabs/doc-qa)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
