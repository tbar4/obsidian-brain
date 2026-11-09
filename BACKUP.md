# Backup

Your last vault was destroyed. Treat backup as part of setup, not an extra.

## Minimum, do this today

1. In the vault folder, run:
   ```
   git init
   git add .
   git commit -m "Initial vault from template pack"
   ```
2. Create a private remote repo, for example on GitHub, and push it.
3. Commit at the end of each writing or research session. One line is enough:
   ```
   git add .; git commit -m "Daily notes and thesis reading"; git push
   ```

## Second copy

Pick one:

- Obsidian Sync, paid, syncs settings and plugins too.
- A cloud folder, for example iCloud Drive, Dropbox, or Synology Drive, with the vault folder inside it.
- A nightly copy to your NAS.

Do not rely on one copy only. Git plus one sync copy is the target.

## What not to put in git

Create a `.gitignore` in the vault root with:

```
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.trash/
```

Keep `.obsidian/app.json` and plugin settings in git if you want the same setup on a second machine.

## Recovery test

Once a month, clone the repo to a temp folder and open it in Obsidian. If it does not open clean, fix backup then, not after a loss.

## If a vault is lost again

1. Clone the git repo.
2. Reinstall plugins from `SETUP.md`.
3. Reconnect Readwise and re-sync `07 Library`.
4. Daily Notes and Permanent Notes are in git, so they come back. Only unsynced, uncommitted work is lost.
