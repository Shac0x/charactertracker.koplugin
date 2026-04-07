# Character Tracker — KOReader Plugin

Track characters, relationships, and notes while you read.
Never forget who's who in a long novel — or across an entire series — again.

---

## Features

### Characters
- **Add characters on the fly** from the highlight popup or the Tools menu.
- **Aliases** — track nicknames, titles, house names, alternate spellings.
- **Notes** — add evolving observations as the story progresses; edit or delete any time.
- **Rating** — rate characters from ★ to ★★★★★.
- **Role** — tag as Main, Secondary, Tertiary, Mentioned, Antagonist, or Narrator.
- **Rename** — safely rename a character (relationships pointing to it are updated automatically).

### Relationships
- Link characters with predefined types: **father, mother, son, daughter, brother, sister, spouse, ally, enemy, friend, mentor, servant, master, lover**.
- **Custom relationships** for anything else (squire, rival, betrothed, ...).
- Detail view shows both **outgoing** (→) and **incoming** (←) relationships.
- Tap a relationship to jump to that character's detail view.
- Deleting a character cleans up dangling relationships automatically.

### In-text recognition
- **Underline character names** in the page (toggle in the menu).
  Names and aliases are indexed in the background using KOReader's `findAllText`.
- **Tap any underlined name** to open that character's detail view instantly.
- Re-indexes automatically when characters or aliases are added/edited.

### Highlight integration
- Adds a **Character** button to the highlight popup.
- Selecting text and tapping **Character** offers to register the selection
  as a new character (or warns you if it's already known).

### Series support (shared characters across books)
- **Link a book to a series** to share one character database across multiple books.
- When linking, existing book characters are **merged** into the series
  (aliases and notes are deduplicated).
- **Unlink** at any time — the series file is preserved.
- Manage and **delete** series from the link dialog.
- Perfect for *A Song of Ice and Fire*, *The Wheel of Time*, *Discworld*, etc.

---

## Installation

Copy the `charactertracker.koplugin` folder to your KOReader plugins directory:

```
<koreader>/plugins/charactertracker.koplugin/
```

Then restart KOReader.

---

## Usage

### Adding a character

**From the highlight popup (recommended):**
1. Long-press and select a character's name in the text.
2. Tap **Character** in the popup.
3. Confirm name and add an optional first note.

**From the Tools menu:**
1. **Tools → Character Tracker → Add character**
2. Enter name and optional note.

### Viewing & editing a character

1. **Tools → Character Tracker → Character list**
2. Tap a character to open the detail view.
3. From there: rate, set role, manage notes, manage aliases, manage relationships, rename, or delete.

### Underlining names in the text

1. **Tools → Character Tracker → Underline names in text** (toggle).
2. Tap any underlined name to open its detail view.

> Indexing runs once when the setting changes or when you add/edit characters.
> A dismissible progress dialog is shown.

### Linking a book to a series

1. **Tools → Character Tracker → Link to series**
2. Pick an existing series or create a new one.
3. Existing characters in the current book are merged into the shared series file.

To unlink: open the same menu entry and choose **Unlink from series**.

---

## Data storage

- **Per-book mode** (default): characters are stored as
  `<book_path>.characters.json` next to the book file.
- **Series mode**: characters are stored in
  `<koreader-data>/character_tracker/<series_name>.json`
  and shared by every book linked to that series.

The format is plain JSON — easy to back up, version-control, or edit by hand.

---

## File structure

```
charactertracker.koplugin/
├── _meta.lua    # Plugin metadata
└── main.lua     # Plugin logic
```


---

Suggestions welcome — open an issue.

---

## License

GNU AGPL v3 — same as KOReader.
