# Gurukul — Agent Instructions

Instructions for working within the `gurukul/` directory. These are loaded automatically when an agent accesses files here.

## Lesson Page Conventions

### Frontmatter

Every lesson needs this YAML block:

```yaml
---
title: Lesson Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
track: <track-folder-name>
order: <next number in track>
prerequisites:
  - "[[gurukul/lessons/<track>/prerequisite-lesson]]"
tags:
  - topic-tag
content_type: lesson | briefing | reference
lesson_format: concept | lab | project | drill | case-study
---
```

- `content_type` is always required.
- `lesson_format` is required only when `content_type: lesson`.
- Use the track's folder name (e.g., `vibing`) as the `track` value.

### Structure

See `agents/skills/write_lesson/formats/` for structure guidance per content type. Each format file contains the spine, scope rule, teaching order, and pre-publish checklist for that format.

### Naming
- Use kebab-case: `getting-started-with-claude-code.md`
- Prefix with order number in filename is optional; use `order:` frontmatter instead

## Prompt File Conventions

Every lesson has a corresponding prompt file at `gurukul/prompts/<track>/<lesson-name>.md` that records how it was created and revised. See `agents/skills/write_lesson/SKILL.md` step 6 for the full format.

- The lesson frontmatter includes `prompt:` pointing to its prompt file
- The prompt file frontmatter includes `lesson:` pointing back to the lesson
- Revisions are appended as dated entries when the lesson is later modified

## Testing References

`gurukul/testing/` contains golden reference lessons mirroring the structure of `gurukul/lessons/`. These are snapshots of lessons produced by the write-lesson skill at a known-good state. When the skill or its format/track files change, re-run the original prompts (from `gurukul/prompts/`) and compare against these references to check for regressions. Testing is manual and user-initiated — not automatic.

## Index Conventions

`gurukul/lessons/index.md` is the curriculum overview with ordered tracks. Shows progression paths.

## Lint Checks (Sensei)

| Check | Action |
|-------|--------|
| **Learning gaps** | Topics covered in wiki but missing from lesson tracks → suggest lessons |
| **Broken prerequisites** | Prerequisites pointing to non-existent lessons → fix link or create stub |
| **Order gaps** | Missing or duplicate `order:` values within a track → renumber |
| **Index drift** | Lessons not listed in `gurukul/lessons/index.md` → add to index |
| **Frontmatter** | Lessons missing required YAML fields (`content_type`, `lesson_format` for lessons) → fix |
