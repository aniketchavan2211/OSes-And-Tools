# TMUX - Terminal Multiplexer

tmux is a terminal multiplexer for Unix-like operating systems. It allows multiple terminal sessions to be accessed simultaneously in a single window. It is useful for running more than one command-line program at the same time.

## Features:
- One terminal window
- Many virtual terminals inside it

tmux runs as a server in the background. You attach and detach clients from it at will.

## The tmux hierarchy

tmux has three layers, always remember this order:

1. Session → the outer container
2. Window → like tabs
3. Pane → split views inside a window

## Sessions

start a new session:
```bash
tmux
```

start with a name (naming a session / windows):
```bash
# tmux new -s session-name
tmux new -s lab
```

running `tmux` command open `new session` and named session as ***`lab`***.

Detach the session:

***`Ctrl + b`, ---> `d`***

Pressed `CTRL + b` then leave key, after that press d. ***DON'T HOLD & PRESS key at same time***.

Reattach the session:
```bash
# tmux attach -t session-name
tmux attach -t lab
```
here we reattach session named lab, session is still running in background. session is not ended.
we are just accessing it again.

List all sessions:
```bash
tmux ls
```

`ls` will lists all active sessions.

To kill a session:
```bash
# tmux kill-session -t session-name
tmux kill-session -t lab
```

tmux command with `tmux-session` argument with following named of session, will kill or end the session.

`CTRL + b` use for all press then release.
It says tmux command is next.

## Windows

Create a window:
***`CTRL + b`, ---> `c`***

Next window:
***`CTRL + b`, ---> `n`***

Previous window:
***`CTRL + b`, ---> `p`***

Jump to a window number:
***`CTRL + b`, ---> `0`-`9`***

Rename a window:
***`CTRL + b`, ---> `,`***

## Panes

Split vertically ( left / right ):
***`CTRL + b`, ---> `%`***

Split horizontally ( top / bottom ):
***`CTRL + b`, ---> `"` ***

Move between panes:
***`CTRL + b`, ---> `arrows keys up/down/left/right`***

Resize panes:
***`CTRL + b`, ---> HOLD `ALT` + `arrow keys up/down/left/right`***

Kill a pane:
***`CTRL + b`, ---> `x`***

Tmux also support Copy mode
Enter into copy mode:
***`CTRL + b` ---> `[`***

- use arrows keys (Up/Down/Left/Right) / PgUp (PageUp) / PgDn (PageDown)
- Start Selection `Spacebar`
- copy selection `Enter`

Paste using:
***`CTRL + b` ---> `]`***

## Status bar (bottom line of wisdom)
At the bottom you’ll see:

- Session name
- Window list
- Active window highlighted
- Clock (if configured)

## Configurations

confiurations files lives in:
```bash
~/.tmux.conf
```

Typical beginner tweaks:

- Change prefix to `Ctrl+a`
- Enable mouse support
- Better colors
- Vim-style pane movement

Example minimal sanity config:
```bash
set -g mouse on
setw -g mode-keys vi
```

Reload config without restarting:
`Ctrl + b`, then ---> `:`
```bash
source-file ~/.tmux.conf
```
