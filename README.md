# Repolex Knowledge Graph of cohere-ai/vllm-skills

RDF knowledge graph data for [cohere-ai/vllm-skills](https://github.com/cohere-ai/vllm-skills), parsed by [repolex](https://repolex.ai).

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
rlex download cohere-ai/vllm-skills
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2a9ed1ff5dd822a521a453f49eff84e8dd5a7071
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2a9ed1ff5dd822a521a453f49eff84e8dd5a7071
│           └── chunk-001.nq.gz
├── blob
│   ├── 1757fa81aa3c29220f568cb56e5060d778041fe4.nq.gz
│   ├── 327afe4d59a477676c7b5936421c78c50edc4e35.nq.gz
│   ├── 42e26a0fcdbc96b01965acf5fdaf01941b261dcd.nq.gz
│   ├── 47ea30b335002895e5aca6d54ce076f3552143d4.nq.gz
│   ├── 87e5b645bbb8b0b7c9b1b0653207f133ea0b3c29.nq.gz
│   ├── 9371ac9c57258bdeef097202edfcfed761c9359b.nq.gz
│   ├── a7cfa67e10421b524fad4e843f8a7445e996af76.nq.gz
│   ├── a9c24bfe7ec7e2c74d5a9afe7cf36fd1aa8e3292.nq.gz
│   ├── aeb2f8d8894a03e3cbf61e696f4962830ee80350.nq.gz
│   ├── c4be46d20e2ba16c571eec5273927bc07cbb30ea.nq.gz
│   ├── d43d3886b4d93dac12972252d6f1060e693e4e34.nq.gz
│   └── f857da267c87756bb3e5b73826354021495c365a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2a9ed1ff5dd822a521a453f49eff84e8dd5a7071.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 18 files
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

[cohere-ai/vllm-skills](https://github.com/cohere-ai/vllm-skills)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
