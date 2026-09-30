<div align="center">

![Marginlight — thoughtful story structure, in the margins](assets/marginlight-banner.svg)

# Marginlight

### Keep your voice. Find your story's shape.

[![MIT License](https://img.shields.io/github/license/Martoto/marginlight?style=flat-square&color=8b6b45)](LICENSE)
[![Agent Skill](https://img.shields.io/badge/format-agent%20skill-596b58?style=flat-square)](SKILL.md)
[![Markdown](https://img.shields.io/badge/manuscripts-Markdown-596b58?style=flat-square&logo=markdown&logoColor=white)](#recommended-manuscript-layout)
[![Preservation first](https://img.shields.io/badge/editing-preservation--first-8b6b45?style=flat-square)](#the-marginlight-promise)

**A preservation-first writing skill for shaping a novel without silently rewriting it.**

[Install](#installation) · [How it works](#how-it-works) · [Manuscript layout](#recommended-manuscript-layout)

</div>

## The Marginlight promise

Your manuscript stays yours. Marginlight reads existing Markdown, maps the story's structure, and points out questions worth answering. It preserves voice, imagery, dialogue, events, point of view, tense, chronology, and characterization. Substantive suggestions stay inside clearly labeled braces for you to accept, change, or ignore.

## How it works

- Maps plot points, acts, beats, scenes, and turning points.
- Tracks character arcs, motivations, relationships, and changes.
- Separates what the manuscript states from inferences and open questions.
- Uses actionable markers such as `{PLOT: ...}`, `{ARC: ...}`, `{SCENE: ...}`, and `{CONTINUITY: ...}`.
- Keeps analysis separate from the manuscript unless you ask for inline notes.
- Logs obvious typo fixes and explicitly requested mechanical edits.
- Keeps Markdown as the source and exports derived DOCX, PDF, or EPUB copies on request.

## Installation

Copy this folder into your novel repository:

```text
your-novel-repo/.agents/skills/marginlight/
```

Or install for personal Codex use:

```text
~/.codex/skills/marginlight/
```

Restart Codex if the skill does not appear, then invoke it with:

```text
$marginlight
```

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
  annotated/               # optional working copies with braced notes
  exports/                 # derived clean or annotated exports
  change-log.md
```

Use headings and stable chapter or scene identifiers. Keep structural analysis out of source chapters unless inline annotation is requested.

## A few example notes

```text
{PLOT: establish what causes the next turning point.}
{ARC: show why this decision changes the character's goal.}
{SCENE: add the physical beat that bridges these actions.}
{CONTINUITY: confirm whether the key has already been introduced.}
{AUTHOR: decide whether the speaker is lying or mistaken.}
```

Marginlight does not fill story gaps with invented prose, resolve ambiguity as fact, or rewrite dialogue to “improve flow.” When the text leaves something unanswered, it records the question and leaves the choice to you.

## Exporting

Export a derived copy, never over the Markdown source. For example, with Pandoc:

```bash
pandoc combined.md -o exports/novel.docx
pandoc combined.md -o exports/novel.pdf
pandoc combined.md -o exports/novel.epub
```

Before exporting, choose the clean manuscript, annotated copy, or structure notes. Clean exports exclude placeholders and analysis unless you request them.

## Contributing

Issues and pull requests are welcome. Keep the core promise intact: the author's prose remains authoritative, and substantive suggestions remain visibly marked for the author.

## License

MIT. See [LICENSE](LICENSE).
