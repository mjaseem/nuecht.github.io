# Personal Publishing System: Requirements

## What This Is

A publishing system for long-running, incremental research. I research topics over years — an hour here, an hour there. I need a place to publish what I learn as I learn it, and have it accumulate into something coherent over time.

The system has multiple content types that can reference each other. Currently there are two: **notes** and **articles**. More content types may be added in the future, so the system should not be designed rigidly around just these two.

---

## Notes

Notes are where I write about what I learned and how I learned it. They're personal, first-person, timestamped.

- Each note is standalone and has a permalink I can share (Mastodon, LinkedIn, etc.).
- A note is tagged to one or more topics.
- A note has a short summary for use in previews and sidenotes.

## Articles

Articles are where accumulated knowledge lives. They're impersonal, reference-like, readable top to bottom. No personal narrative in the main text.

- An article belongs to one topic.
- Articles are ordered within a topic by a weight I control (not by date).
- An article has a maturity level: **seedling**, **budding**, or **evergreen**.
- Articles are freely edited. Fixing a typo is invisible — no ceremony, no trace.

## Topics

A topic is a grouping that brings together articles and notes about the same subject.

- A topic page shows: the articles (if any), and all the notes tagged to it.
- A topic with only notes and no articles is valid and should not look incomplete.
- Topics can have an optional description.

---

## Sidenotes: Connecting Articles to Notes

This is the key feature. Articles can reference notes as sidenotes.

- A sentence or section in an article can be linked to a specific note.
- The link shows as a subtle marker in the text.
- On desktop, the sidenote content appears in the margin — showing the note's title, date, summary, and a link to the full note.
- On mobile, the sidenote expands inline when tapped.
- The article text is the knowledge. The sidenote is the personal journey of how I arrived at it.

## Personal Context Blocks

Articles can also contain collapsible blocks of personal commentary that aren't tied to a specific note. These are hidden by default and expandable by the reader.

---

## Syndication

- An RSS feed of all notes.
- An RSS feed per topic.
- Notes should have proper meta tags for link previews on social platforms.

---

## Design

- Minimal, text-focused, no clutter.
- Comfortable reading width for body text, with room for sidenotes in the margin on desktop.
- Responsive — sidenotes adapt to mobile.
- Dark mode support.
- No JavaScript required for core reading experience (sidenotes, personal context blocks).

---

## Hosting & Authoring

- Static site, hosted on GitHub Pages.
- Deployed automatically on push.
- I write in markdown files locally in Neovim.
- Git-backed.

---

## Priority

**Phase 1**: Notes, topics, homepage, RSS feed, deployed to GitHub Pages. I should be able to start writing immediately.

**Phase 2**: Articles, topic pages that aggregate both content types, maturity indicators.

**Phase 3**: Sidenotes connecting articles to notes, personal context blocks, backlinks from notes to articles that reference them.

**Phase 4**: Per-topic feeds, social meta tags, dark mode, search.
