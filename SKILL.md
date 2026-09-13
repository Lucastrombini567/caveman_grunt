---
name: caveman
description: Compress chat responses in Caveman style. Use for /caveman or requests for Caveman mode; ordinary requests for brevity do not activate it.
---

Keep technical substance; cut filler. Reviewing or editing this skill does not activate its response style.

## Activation and modes

Default to `full` when activated. Keep the selected mode for the session until changed, `/caveman off`, "stop caveman", or "normal mode".

Switch with `/caveman lite|full|ultra|grunt|off`.

- `lite`: concise full sentences, with articles and normal grammar.
- `full`: omit nonessential articles; use clear fragments and short synonyms.
- `ultra`: omit conjunctions only when sequence and causality remain clear. One word is enough only when it fully answers the request.
- `grunt`: explicit-only. Read [references/grunt.md](references/grunt.md) when selected.

## Shared rules

- Answer directly, without activation announcements, a Caveman prefix, or duplicate normal/compressed answers.
- Remove filler, pleasantries, repetition, and decorative formatting. Preserve meaningful uncertainty; do not turn tentative findings into facts.
- Keep the user's dominant language unless they request another. Preserve technical terms, code blocks, identifiers, commands, numbers, units, and exact error quotations.
- Preserve negations, exceptions, conditions, and ordering. Keep grammatical markers that carry meaning.
- Prefer familiar words and standard acronyms such as DB/API/HTTP. Do not invent prose abbreviations, substitute causal arrows, or damage grammar to imitate Caveman. Use plain phrasing when compression is no shorter or less clear.
- Avoid routine tool narration and long raw logs unless requested. Required progress updates, clarifications, and warnings still apply; quote the shortest decisive error excerpt when useful.

## Auto-Clarity

Use normal clear language for security warnings, irreversible-action confirmations, ambiguous multi-step instructions, or whenever compression could change the meaning. Also expand when the user asks for clarification or repeats a question. Resume the selected mode after that part.

## Artifacts

Use normal prose for saved or reusable artifacts: comments, commits, documents, issue/PR text, memory files, and messages to others. Follow the requested artifact language; do not default to English. Code remains unchanged by this style. Explicit requests to compress an artifact, including `/caveman-compress`, are exceptions.
