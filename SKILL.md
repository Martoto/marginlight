---
name: marginlight
description: Use when a novelist wants existing prose analyzed into plot points, character arcs, scene structure, continuity notes, or author-editable placeholders while preserving the manuscript.
metadata:
  short-description: Organize and annotate novel manuscripts without rewriting them
---

# Marginlight

## Core contract

Treat the author's prose as source material, not as a draft to improve. Preserve voice, imagery, dialogue, events, point of view, tense, chronology, and characterization. The only unmarked text changes allowed are obvious typing errors and explicitly requested mechanical consistency changes, such as a global character-name correction. Record every mechanical change.

Any substantive invention, bridge, expansion, interpretation, or proposed rewrite must be visibly enclosed in braces. Never turn a placeholder into ordinary prose.

## Workflow

1. Inventory the Markdown files and establish their order. Do not overwrite or rename source files without explicit permission.
2. Read the material before interpreting it. Separate facts stated in the text from inferences, open questions, and suggestions.
3. Create structural notes for plot points, acts/beats, character arcs, scene purposes, setting, motifs, continuity, and unresolved questions.
4. Produce an annotated working copy only when useful. Keep the original text intact and mark additions inline with a typed placeholder.
5. Run a preservation check: compare source and working prose, inspect every non-mechanical difference, and confirm that all substantive additions are braced.
6. Export only on request. Export a derived file, never the Markdown source, and identify which variant was exported.

## Placeholder contract

Use concise, actionable braces. Prefer these labels:

- `{PLOT: establish what causes the next turn.}`
- `{ARC: show why this decision changes the character's goal.}`
- `{SCENE: add the sensory or physical beat that bridges these actions.}`
- `{CONTINUITY: confirm whether the key has already been introduced.}`
- `{AUTHOR: decide whether the speaker is lying or mistaken.}`

Place a placeholder at the point where the author should work. Do not write a polished replacement passage outside braces. If several possibilities exist, list them inside one labeled placeholder rather than choosing silently.

## File layout

For a manuscript project, use a predictable Markdown package:

```text
novel/
  manuscript/              # author source; never overwrite by default
    01-chapter-title.md
  structure/
    plot-points.md
    character-arcs.md
    scene-outline.md
    continuity.md
    open-questions.md
  annotated/                # optional copies with mechanical fixes and braces
    01-chapter-title.md
  exports/                  # derived DOCX, PDF, EPUB, or combined Markdown
  change-log.md
```

Use headings, lists, tables, and stable chapter/scene identifiers so the Markdown remains readable and convertible. Keep analysis separate from the manuscript unless the author asks for inline annotations.

## Mechanical changes

Allowed examples include fixing `teh` to `the`, correcting punctuation that is clearly mistyped, standardizing a requested spelling, or changing `Elianne` to `Elian` after the author identifies the canonical name. Do not silently fix an intentional fragment, dialect, unusual spelling, factual inconsistency, or stylistic choice.

Log each change in `change-log.md` with file, location, original, replacement, and reason. If the requested change affects plot meaning, ask instead of applying it.

## Export

Keep Markdown as the source of truth. On request, combine the intended files in story order and export the derived copy to the requested format. If Pandoc is available, typical commands are:

```text
pandoc combined.md -o exports/novel.docx
pandoc combined.md -o exports/novel.pdf
pandoc combined.md -o exports/novel.epub
```

Before export, confirm whether the author wants the clean manuscript, the annotated version, or structure notes. Never include analysis or placeholders in a clean export unless explicitly requested.

## Common mistakes

- Filling a gap with invented backstory instead of `{PLOT: ...}` or `{SCENE: ...}`.
- “Improving flow” by rewriting sentences without a logged mechanical reason.
- Resolving ambiguity as fact instead of recording it in `continuity.md`.
- Mixing plot analysis into the source chapter.
- Exporting over a source file or presenting a derived export as the canonical manuscript.

## Final verification

Report the files created, source files preserved, mechanical changes made, placeholders added, unresolved questions, and export variant. If no substantive prose was changed, say so explicitly.
