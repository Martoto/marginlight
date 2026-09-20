# Novel Structure Editing

`novel-structure-editing` is a preservation-first skill for organizing and developing novel manuscripts without silently rewriting the author’s voice.

It reads existing Markdown, extracts the story’s structure, identifies continuity questions, and places suggested additions in visible `{braced placeholders}` for the author to write and expand.

## What it does

- Organizes plot points, acts, beats, scenes, and turning points.
- Maps character arcs, motivations, relationships, and unresolved changes.
- Separates textual facts from inferences, open questions, and suggestions.
- Adds typed placeholders such as `{PLOT: ...}`, `{ARC: ...}`, `{SCENE: ...}`, and `{CONTINUITY: ...}`.
- Preserves the author’s prose, voice, imagery, dialogue, events, point of view, tense, and characterization.
- Allows only obvious typing errors and explicitly requested mechanical consistency changes, with a change log.
- Keeps Markdown as the source of truth and supports derived DOCX, PDF, and EPUB exports through tools such as Pandoc.

## Installation

For a repository-specific installation, copy this folder into:

```text
your-novel-repo/.agents/skills/novel-structure-editing/
```

For personal Codex use, place it in your user skills directory, for example:

```text
~/.codex/skills/novel-structure-editing/
```

or:

```text
~/.agents/skills/novel-structure-editing/
```

Restart Codex if the skill does not appear, then invoke it explicitly with:

```text
$novel-structure-editing
```

It can also be selected automatically when a request involves novel structure, plot arcs, continuity, or author-editable placeholders.

## Recommended manuscript layout

```text
novel/
  manuscript/              # original author source; never overwrite by default
    01-chapter-title.md
  structure/
    plot-points.md
    character-arcs.md
    scene-outline.md
    continuity.md
    open-questions.md
  annotated/               # optional copies with mechanical fixes and placeholders
  exports/                 # derived clean or annotated exports
  change-log.md
```

Keep structural analysis separate from the source manuscript unless inline annotations are explicitly requested.

## Preservation rule

The skill must not “improve flow,” invent backstory, resolve ambiguity, rewrite dialogue, or add polished connective prose outside braces. When the source does not answer a question, it records the question instead of choosing an answer silently.

Examples:

```text
{PLOT: establish what causes the next turning point.}
{ARC: show why this decision changes the character’s goal.}
{SCENE: add the physical beat that bridges these actions.}
{CONTINUITY: confirm whether the key has already been introduced.}
{AUTHOR: decide whether the speaker is lying or mistaken.}
```

## Exporting

Export a derived copy, never the Markdown source. For example:

```bash
pandoc combined.md -o exports/novel.docx
pandoc combined.md -o exports/novel.pdf
pandoc combined.md -o exports/novel.epub
```

Before exporting, choose whether the output should contain the clean manuscript, the annotated manuscript, or structure notes. Clean exports should not contain placeholders or analysis unless explicitly requested.

## Contributing

Issues and pull requests are welcome. Changes should preserve the central contract: the author’s prose remains authoritative, and substantive suggestions stay visibly marked for the author.

## License

Released under the [MIT License](LICENSE).
