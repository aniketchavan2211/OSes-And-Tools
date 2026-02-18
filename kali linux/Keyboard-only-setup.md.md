# Kali GNOME DE Keyboard only setup

## System

Lock screen : `Super + L`

Log out : `Ctrl + Alt + Delete`

Power Off : Not Set

Restart : Not Set

Show all Applications : `Super + A`

Show notification bar : `Super + v`

Run command prompt  : `Alt + F2`

Hide all normal windows : `Ctrl + Super + d`

Switch Applications : `Super + Tab`

Open quick settings menu : `Super + s`
## Workspaces

Switch to first workspace : `Super + Home`

Switch to last workspace : `Super + End`

Switch workspace on left : `Super + Page Up`

Switch workspace on right :  `Super + Page Down`

Move windows to one workspace to left : `Shift + Super + Page Up`

Move windows to one workspace to right : `Shift + Super + Page Down`

Move windows to first workspace : `Shift + Super + End`

Move window to last workspace : `Shift + Super + End`

## Windows

Windows = Applications windows

Switch Applications : `Alt + Tab`

Switch applications : `Alt + Esc(ape)`

Switch Windows of an application : `Super + (backtick `)`

Opens windows menu : `Alt + Space`

Tile window left/right : `Super + Arrow left (←) / Arrow right (→)`

Close windows : `Alt + F4`

Hide windows : `Super + H`

Maximize / Minimize Windows : `Super + arrow UP + arrow DOWN`

Move windows : `Alt + F7`
## Screenshots

Take a screenshot : `Shift + Print`

Take a screenshot interactively : `Print`

Take a screenshot of windows : `Alt + Print`

## Gnome Terminal 

Open terminal : `Ctrl + Alt + T`

Open terminal : `Super + T`

Copy : `Ctrl + Shift + C`

Paste : `Ctrl + Shift + V`

Clear screen : `Ctrl + L`

Exit shell : `Ctrl + D`

Start of command : `Ctrl + A`

End of command : Ctrl + E

Word Backward : `Alt + B`

Word Forward : `Alt + F`

Search command : `Ctrl + R`

## Tmux

Custom Prefix : `Ctrl + A`

Default Prefix : `Ctrl + B` ( Unbinded )

### Windows 

Create a new windows : `Prefix + C`

Switch to next windows : `Prefix + N`

Switch to previous windows : `Prefix + P`
### Panes

#### Navigation

Switch to Left Pane : Prefix ( `Ctrl + a` ) + `h` / Prefix + `←` Arrows Left

Switch to Down Pane : Prefix ( `Ctrl + a` ) + `j` / Prefix + `↓` Arrows Down

Switch to Up Pane : Prefix ( `Ctrl + a` ) + `k` / Prefix + `↑` Arrows Up

Switch to Right Pane: Prefix ( `Ctrl + a` ) + `l` / Prefix + `→` Arrows Right

Close or Kill Pane : Prefix `Ctrl + a` + `X`
#### Splits 

Splits panes Horizontally : Prefix ( `Ctrl + a`) + - ( **hyphen / dash / minus sign** )

Splits panes vertically : Prefix ( `Ctrl + a` ) + `|` (**pipeline**)

Default Horizontally : `Ctrl + b` + `"`

Default Vertically : `Ctrl + b` + `%`

#### Resize 

Resize up/down/left/right : ***HOLD Prefix ( `Ctrl + a` )*** + capital letters `HJKL` / ←↑↓→ Arrows

Resize left : Prefix ( `Ctrl + a` ) + **Hold `H`**

Resize down : Prefix ( `Ctrl + a` ) + **Hold `J`**

Resize up : Prefix ( `Ctrl + a` ) + **Hold `K`**

Resize right : Prefix ( `Ctrl + a` ) + **Hold `L`**
## Mozilla Firefox 

Open Mozilla Firefox : `Super + b`

open a new tab : `Ctrl + t`

close a tab : `Ctrl + w`

Reopen a tab : `Ctrl + Shift + t`

Switch between tab : `Ctrl + Tab`

Switch tab to left : `Ctrl + Page Up`

Switch tab to right : `Ctrl + Page Down`

Page Backward / Forward : `Alt + ← / →`

Find on page : `/` ( **Forward Slash** ) 

open new windows : `Ctrl + n`

Focus on address bar : `Ctrl + l`

### Monkeytype

Restart test : `Tab + Enter`

Command line : `Esc / Ctrl + Shift + p`
## Neovim

Leader key : `Space`

### Windows Navigation

Windows are like tmux pane.

**Normal Mode**

***Spliting***
Split windows into Horizontally : `Space / Leader key + sh`

Split windows into Vertically : `Space / Leader key + sv`

***Switching***
Switch windows to left : `Ctrl + h`

Switch windows to down : `Ctrl + j`

Switch windows to up : `Ctrl + k`

Switch windows to right : `Ctrl + l`

***Resizing***
Resize windows left : `Leader key + wh`

Resize windows down : `Leader key + wj`

Resize windows up : `Leader key + wk`

Resize windows right : `Leader key + wl`

***Closing***
Close Windows : `Leader key + wc`

Close others windows : `Leader key + wo`

### Tabs Navigation

Create Tabs : `Leader key + tn`

Switching Left :  `Leader key + th`

Switching Right : `Leader key + tl`

Close Tabs : `Leader key + tc`

### File Actions

File opened in buffer Tabs

**Normal Mode**

Write / Saved file : `Space / Leader key + w`

Switching left opened file buffer : `Shift + h`

Switching right opened file buffer : `Shift + l`

Quit / Exit Neovim : `Space / Leader key + q`

Safe Quit ask if unsaved changes : `Space / Leader key + qq`

Save & Quit : `Space / Leader key + wq`

Force Quit without saving : `Space / Leader key + qx`

### Buffer Navigation

Previous buffer file opened :  `Shift + h`

Default previous buffer opened : `Space / Leader key + bp`

Next buffer file opened : `Shift + l`

Default next buffer opened : `Space / Leader key + bn`

Close File Buffer : `Space / Leader key + bd`

Jump to number opened file : `Space / Leader key 1..9`

### Rust Helpers

cargo check : `Space / Leader key + rc`

cargo build : `Space / Leader key + rb`

cargo run : `Space / Leader key + rr`

cargo format : `Space / Leader key + rf`

### File Explorer

***(Netrw File Explorer)***

**Notice on uppercase and lowercase**
> Keybindings works only in Netrw File Explorer, if use other you need to config by your own.

Open file explorer : `Space / Leader key + e`

Open File or Directory : `Enter`

Create new file : `%`

Create new directory : `d` 

Rename : `R`

Delete : `D`

Quit Explorer : `Shift + q`

## Obsidian Vault 

