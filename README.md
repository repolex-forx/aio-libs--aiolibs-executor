# Repolex Knowledge Graph of aio-libs/aiolibs-executor

RDF knowledge graph data for [aio-libs/aiolibs-executor](https://github.com/aio-libs/aiolibs-executor), parsed by [repolex](https://repolex.ai).

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
rlex download aio-libs/aiolibs-executor
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a215e91a8183ac4ff2ba4d116fb1777c123b468a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a215e91a8183ac4ff2ba4d116fb1777c123b468a
│           └── chunk-001.nq.gz
├── blob
│   ├── 15f89fabd8e3f682df21af279aec8c6a98b22cc0.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 419e3339806d6f07b16614b898d78920f664326d.nq.gz
│   ├── 6dd6e031a4ca96132b4f40033de54df42a89c487.nq.gz
│   ├── 7ee3ea635311816cc7ab5e90c1f115b07b96a99c.nq.gz
│   ├── a6315328ba24a48a672352327ef388da74c08746.nq.gz
│   ├── b216a24f2802b43380964aa09f2cafc4cbf6de9e.nq.gz
│   ├── cbdc0b973c61bc567b4791b2564d8c0fd672adcf.nq.gz
│   ├── cc568a5896a6d9455dd50a18762d363bd3af85de.nq.gz
│   ├── d422cc848219eb236aea8a2a40cb3f56e47ceded.nq.gz
│   ├── da81175521124c168c048fc570a6c61c7f183eaa.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── fad53adc18525c7d511b7546f86346b50048fe1f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a215e91a8183ac4ff2ba4d116fb1777c123b468a.nq.gz
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

[aio-libs/aiolibs-executor](https://github.com/aio-libs/aiolibs-executor)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
