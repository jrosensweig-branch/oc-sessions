# oc-sessions

A terminal picker for [OpenCode](https://opencode.ai) sessions across every project.

OpenCode only lists sessions for the current directory. `oc-sessions` reads the local OpenCode database and lets you resume any session from anywhere.

## Requirements

- Python 3.10+
- [OpenCode](https://opencode.ai) on `PATH`
- A terminal (the picker is interactive)

## Install

```bash
git clone https://github.com/jrosensweig-branch/oc-sessions.git
chmod +x oc-sessions/oc-sessions
ln -s "$(pwd)/oc-sessions/oc-sessions" ~/.local/bin/oc-sessions
```

Make sure `~/.local/bin` is on your `PATH`.

## Usage

```bash
oc-sessions
```

- `↑` `↓` / `j` `k` — move
- `Enter` — resume (original directory or current directory)
- `g` — assign the session to a group
- `Esc` — quit
- `PgUp` / `PgDn` — page
- `Home` / `End` — jump to first / last session

In iTerm, resume splits a pane to the right and leaves the picker open on the left. Outside iTerm, resume replaces the picker as before.

If a session’s original directory is gone, resuming there recreates it.

## Theme

The picker follows your OpenCode theme (`/themes` or `tui.json`). Theme files are cached under `~/.cache/oc-sessions/themes`.

## Groups

Groups are local to `oc-sessions`, not OpenCode pins. They are stored at:

```
~/.local/state/oc-sessions/groups.json
```

That file is per-user and is not part of this repo.
