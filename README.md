# Caveman

Talk like smart caveman. Same brain, fewer tokens.

[Leia em português](README.pt-BR.md)

## What it does

Compress model responses to Caveman-style prose by dropping articles, filler,
pleasantries, and repetition. Preserve meaningful uncertainty, technical detail,
code blocks, error strings, and symbols. Results depend on model and workload;
no aggregate reduction or quality-equivalence claim is published. The selected
mode persists until changed or stopped.

Four intensity levels:

| Level | What changes |
| --- | --- |
| `lite` | Drop filler. Sentences stay full. Professional but tight. |
| `full` | Default. Drop nonessential articles; clear fragments and short synonyms are OK. |
| `ultra` | Shortest clear phrasing. No invented abbreviations or causal arrows. |
| `grunt` | Explicit-only. Minimal complete answers or brief action status. |

For warnings, irreversible actions, ambiguous sequences, and clarification,
Caveman returns to clear normal prose for that part.

## How to use

Copy this repository to your skills directory, preserving its structure:

```text
skills/
└── caveman/
    ├── SKILL.md
    └── references/
        └── grunt.md
```

Then use:

```text
/caveman              # full mode (default)
/caveman lite         # lighter compression
/caveman ultra        # strongest normal-language compression
/caveman grunt        # minimal complete answers and action status
/caveman off          # return to normal prose
```

You can also say “stop caveman” or “normal mode”.

## Example

Question: “Explain database connection pooling.”

Normal prose:

> Connection pooling reuses open database connections instead of creating a new connection for each request, reducing connection setup overhead.

Caveman (`full`):

> Pool reuses open DB connections. Less setup per request.

Caveman (`ultra`):

> Reuse DB connections. Reduce setup overhead.
