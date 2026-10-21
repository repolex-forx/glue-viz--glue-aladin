# Repolex Knowledge Graph of glue-viz/glue-aladin

RDF knowledge graph data for [glue-viz/glue-aladin](https://github.com/glue-viz/glue-aladin), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-aladin
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4c68a8ee46bab848072a3a95632e278821211ac7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4c68a8ee46bab848072a3a95632e278821211ac7
│           └── chunk-001.nq.gz
├── blob
│   ├── 02f0ff373fe285ead3c3b443896bf20f23c7f422.nq.gz
│   ├── 049bc121b522a41e45857762045e4f48e4166074.nq.gz
│   ├── 052225563afceb3b42533b0a90c7de107007ad66.nq.gz
│   ├── 122d9b57b29adce3540d865892e6f58b92751842.nq.gz
│   ├── 4f46c5f9d8c98fd24a5079673cb234badb6b2651.nq.gz
│   ├── 572a199b15ef560911c0cfeaa018dfa8329b4beb.nq.gz
│   ├── 65bb76bac6d116590ad3423d21645483946e7e8f.nq.gz
│   ├── 6dc732713370b194a3803a11639032fb0f6914b8.nq.gz
│   ├── 77751b1c45a486f1baccb43034be83ece74dbab1.nq.gz
│   ├── 7cb5d405f79dbc9684296fc57b8eeeab16694cfa.nq.gz
│   ├── 7d9ccd8b9aa6f95a2d333f4de752ff0d84de5788.nq.gz
│   ├── 8d445604a95ac6a51874b6a1cbc812920719839a.nq.gz
│   ├── 937b355cc1150e36ebad56e55dcfd991426bbfc1.nq.gz
│   ├── 938f13030e4f1306944123ed62d1d32282bd773c.nq.gz
│   ├── 93c279c485cb54d8807f5e5134ce94b6e9259a5f.nq.gz
│   ├── 9ec8fad727b53353958640dcc3798e126929d168.nq.gz
│   ├── a1c7520b5ce970776022321de55592297e4719e0.nq.gz
│   ├── a3db2a9c11fbc6e3efe2e6ad3fd41bed32a519a8.nq.gz
│   ├── b972268a8ed5a6b14699f97c3f21bc2e13911710.nq.gz
│   ├── c946364bd7bf03e8b2287269172193350dbaf43c.nq.gz
│   ├── ded1a8eb9edc0f5ece7ccc65feeb96ece6ef9139.nq.gz
│   ├── e2d55b437c39e11d11796850403aa3965146f343.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e73388a9eeb5fa084711efafc111dd0226c751fe.nq.gz
│   └── f1002abca95eca1b691ce47e25bc7ce88690496a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4c68a8ee46bab848072a3a95632e278821211ac7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 33 files
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

[glue-viz/glue-aladin](https://github.com/glue-viz/glue-aladin)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
