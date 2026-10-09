# Repolex Knowledge Graph of modelcontextprotocol/ext-skills

RDF knowledge graph data for [modelcontextprotocol/ext-skills](https://github.com/modelcontextprotocol/ext-skills), parsed by [repolex](https://repolex.ai).

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
rlex download modelcontextprotocol/ext-skills
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 167da6c0d42c247a8f8470228a10ca711e3f6c45
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 167da6c0d42c247a8f8470228a10ca711e3f6c45
│           └── chunk-001.nq.gz
├── blob
│   ├── 03bdbb456617eaf3d1dc9472832b94da171243e6.nq.gz
│   ├── 04a2b6fcde4b92087b38319672137a55558a5f45.nq.gz
│   ├── 090bba965243f4fbef858b96474ecb1104aeceb0.nq.gz
│   ├── 1830046e0ce1235e1d3ee00a08dfbdf9d49c128d.nq.gz
│   ├── 23b80e55ae4989763447aeba36a29087378c5463.nq.gz
│   ├── 253fe339c43fd4a24a4af605c3bf2afd355bb666.nq.gz
│   ├── 27e2d590bf65a954182cd80bf7fcd2bebe4385d4.nq.gz
│   ├── 2d79909918dfed545a9a7293e3f2a92f6aa79c00.nq.gz
│   ├── 3d572e37b2e1daa131da2c34744fd410bd41aed9.nq.gz
│   ├── 3f14688b7de6a2676d0589494c4e8ff5ad31d6ee.nq.gz
│   ├── 45ebd13abf5c0591c5bf4c58da79f8f485dc2995.nq.gz
│   ├── 47d520ff92ec7b79a0e14bd4c6a944489d357b65.nq.gz
│   ├── 58f30832db4165da68156eca5f7983b56c605edf.nq.gz
│   ├── 5c5439ff86d113f1a8e97cc0d03aef2889f31c53.nq.gz
│   ├── 631e6355f77d0070283ecf97e081e42d35beb76e.nq.gz
│   ├── 6df8d2a49b5de24c57d9cb909458ea6bfb2a6e4c.nq.gz
│   ├── 6eaed0a9b419d7da71d50a90843a438ab39c700f.nq.gz
│   ├── 6f7b477afb43add9c63bfc49e403dedc477edfed.nq.gz
│   ├── 729897425601c3b6d63d18d82ed42bdd9c547e7b.nq.gz
│   ├── 77481b22ec1e329130e170624d21c1fad1f58921.nq.gz
│   ├── 81a6d2610a34ed5b18db2be6beab2ddd86211146.nq.gz
│   ├── 824c66badb3c07635eb34d7619e75d7c2a26c6b0.nq.gz
│   ├── 8b820e7a2f8ec152aaad423c68ae05978e706fc1.nq.gz
│   ├── 924bda51bdbd1593ddd11f297c57ffa52e6b5568.nq.gz
│   ├── 9c82bf9a961e7d13785b3cbf13d2e165de2fd2f5.nq.gz
│   ├── acbb119ff6b084e1f317a9bad189be1b20385cb6.nq.gz
│   ├── b4d8ed611fe95b26da68f5f47b7d9365e9d80dbe.nq.gz
│   ├── bdb97a77431ba35ef47dec7d4ce31a61b7e2be37.nq.gz
│   ├── c4b06c579b9355c29d4551f6bbe87aff7aab093c.nq.gz
│   ├── d5cc735acdd7f32de7a8fd0433dfcba09f61d0a1.nq.gz
│   ├── d5decd706983164dbd75e563c909a00f2b01bbc0.nq.gz
│   ├── da8a45bce528f5cb5a90b4253d5fb86a04ea3dd2.nq.gz
│   ├── eb18c6664725c607294a3f9e673f98542d5572a0.nq.gz
│   └── eeccc865aceecf44b7bf4fe9cc9f4a47f33e8cce.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 167da6c0d42c247a8f8470228a10ca711e3f6c45.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[modelcontextprotocol/ext-skills](https://github.com/modelcontextprotocol/ext-skills)

---
*Parsed on 2026-10-09 by [repolex](https://repolex.ai)*
