# Setup

## 1. Create the vault

1. Copy this whole folder to where you keep vaults, for example `~/Documents/Obsidian/Trevor Vault`.
2. In Obsidian, choose Open folder as vault, pick that folder.
3. Do `BACKUP.md` step 1 now, before adding notes.

## 2. Core settings

- Settings > Files and links: Default location for new notes: In the folder specified below. Set it to `00 Inbox`.
- Settings > Files and links: Default location for new attachments: In subfolder under current folder. Use `assets`.
- Settings > Daily notes: Date format `YYYY-MM-DD`, New file location `01 Journal/Daily`, Template `08 Templates/Daily Note.md`.
- Settings > Templates: Template folder location `08 Templates`.

## 3. Community plugins to install

| Plugin | Why | Key setting |
| --- | --- | --- |
| Templater | Date math and prompts in templates | Template folder: `08 Templates` |
| Dataview | Project and writing dashboards | Enable JavaScript queries: off, unless you need it |
| Calendar | Click a date to open a Daily Note | No extra setup |
| Tasks | Query tasks across Daily Notes | No extra setup |
| Readwise Official | Sync highlights to `07 Library` | See below |

## 4. Readwise sync

1. Install Readwise Official from Community Plugins.
2. Connect with your Readwise token.
3. Set the sync folder to `07 Library`.
4. Set the template to the Literature Note shape in this pack: title, author, highlights verbatim, your take as a link to a Permanent Note.
5. Run one sync, check one book, then leave it on auto sync.

Rule: do not edit a synced highlight in place. If you disagree with it, write a Permanent Note.

## 5. Templater notes

Templates in this pack use plain Obsidian template syntax `{{date}}` and `{{title}}` where possible, so they work without Templater too.

If you use Templater, replace the date line in Daily Note with:

```
<% tp.file.title %>
```

And use Templater folder templates: Daily Notes folder `01 Journal/Daily` uses Daily Note, `00 Inbox` uses Fleeting Note.

## 6. Dataview starter queries

Put these in a Dashboard note if you want one. They are optional.

### Open projects

```dataview
TABLE status, deadline
FROM "02 Projects"
WHERE status != "Done"
SORT deadline ASC
```

### Writing pipeline

```dataview
TABLE status, thesis
FROM "06 Writing"
SORT file.name ASC
```

### Tasks due this week

```dataview
TASK
FROM "01 Journal/Daily"
WHERE !completed
SORT file.name DESC
LIMIT 30
```

## 7. Tags to use, sparingly

Use folders first, tags second. Keep this short list only:

- `#project/active`, `#project/done`
- `#area`
- `#writing/idea`, `#writing/draft`, `#writing/published`
- `#seed` for a Permanent Note candidate, `#permanent` for a finished one
- `#readwise` for synced Library notes

Do not invent a new tag per topic. Topics are links between Permanent Notes.
