# Repolex Knowledge Graph of huggingface/ioi

RDF knowledge graph data for [huggingface/ioi](https://github.com/huggingface/ioi), parsed by [repolex](https://repolex.ai).

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
rlex download huggingface/ioi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f4f055b81214f755287c1c23cacb33db254e8c74
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f4f055b81214f755287c1c23cacb33db254e8c74
│           └── chunk-001.nq.gz
├── blob
│   ├── 0381a0ad72adfa1ce6d93ade8fb54dc7e9054d32.nq.gz
│   ├── 073f37f5dde48c68207fed0148bbfb5262e9787c.nq.gz
│   ├── 09374c914e817e00a7be05ca503375a00056103b.nq.gz
│   ├── 20d10a4f999fa577974aa95d817c3f38f102c275.nq.gz
│   ├── 21ede1bc304c4d26dd82d78051ef4da0c8cfa733.nq.gz
│   ├── 24d741e51a610accf8f3c7f260f922bd5d438271.nq.gz
│   ├── 38d0973fc61f52b458b830a2c08d0286da519d36.nq.gz
│   ├── 39d250fa7094c938d45f273eb3753febfaa03d63.nq.gz
│   ├── 4905c82b3b1234bd9966cb2edace63bb509ecbea.nq.gz
│   ├── 51e3cc3829bcd8c73cf164f113821825057c043e.nq.gz
│   ├── 7092f98dfc507409450c584c47053e2770621a8f.nq.gz
│   ├── 7accd271d9488895afb9dc7c4a5867dda3d0b466.nq.gz
│   ├── 85d4f8792c507f686595ede0c18cf76d6d991edc.nq.gz
│   ├── 88cd9ec258f0d4afa4aa72a01019a8b7bc7be41c.nq.gz
│   ├── 8b79582504cd94acf08778b179c2a877674a04b9.nq.gz
│   ├── 8b9b4ac554e4b3e5f0effa5c73d945e57dfc2171.nq.gz
│   ├── 9a6daf13d24801328b0276565dbe084af650e699.nq.gz
│   ├── 9ca6659cc6c203928f4195bc8cfb4f6ac4ae0142.nq.gz
│   ├── a7830d93e6bfb8b2df64b85fa958373ad6bfc713.nq.gz
│   ├── aff546f689edebbca0e901aada704622de2eecbe.nq.gz
│   ├── b1acf4c1b3aaaa2a14d0954acf1295d4bf85b456.nq.gz
│   ├── b5d37d64ddac78d4834a5bf252755096fb58c2de.nq.gz
│   ├── d2dd3489c5015b69a1f803d865a0b72462a39cf3.nq.gz
│   ├── dfc8bb7febfcbd6e0fb62b93e2c58ab8278cfdcf.nq.gz
│   ├── e7abca3eb929b79aeb4fad2ed1766c23bae9e456.nq.gz
│   ├── f019428654373c04a7aebf34ee85cac04e847248.nq.gz
│   ├── f939e8feb7c8e146fb07afc01c137f1416c5dc56.nq.gz
│   └── f9cf320e270fd588749c9c6760835bfc7a221097.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f4f055b81214f755287c1c23cacb33db254e8c74.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 36 files
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

[huggingface/ioi](https://github.com/huggingface/ioi)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
