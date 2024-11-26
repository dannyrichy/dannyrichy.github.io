---
layout: niendefault
title: VIM shortcuts
category: "Dev Tutorial"
---
## VIM

Date: 26/11/2024

## Basics

| Command | Description                     |
|---------|---------------------------------|
| `:w`    | Save changes                   |
| `:q`    | Quit Vim                       |
| `i`     | Enter insert mode              |
| `Esc`   | Exit insert mode               |

## Navigation

| Command | Description                    |
|---------|--------------------------------|
| `h`     | Move left                     |
| `j`     | Move down                     |
| `k`     | Move up                       |
| `l`     | Move right                    |

## Editing

| Command | Description                           |
|---------|---------------------------------------|
| `x`     | Delete the character under the cursor|
| `dd`    | Delete the current line              |
| `yy`    | Copy (yank) the current line         |
| `p`     | Paste after the cursor               |

## Search and Replace

| Command         | Description                           |
|-----------------|---------------------------------------|
| `/pattern`      | Search for pattern                   |
| `n`             | Repeat the last search forward       |
| `N`             | Repeat the last search backward      |
| `:%s/old/new/g` | Replace all occurrences of 'old' with 'new' |

## Tabs and Windows

| Command        | Description                   |
|----------------|-------------------------------|
| `:tabnew`      | Open a new tab                |
| `:split`       | Split the window horizontally |
| `:vsplit`      | Split the window vertically   |
| `Ctrl-w w`     | Switch between windows        |

## Macros

| Command  | Description                     |
|----------|---------------------------------|
| `qa`     | Start recording macro in register `a` |
| `q`      | Stop recording                  |
| `@a`     | Execute macro in register `a`   |
| `@@`     | Replay the last executed macro  |

## Exit Commands

| Command      | Description                    |
|--------------|--------------------------------|
| `:w`         | Save the current file          |
| `:wq`        | Save and quit                  |
| `:q!`        | Quit without saving            |
| `:x` or `ZZ` | Save and quit                  |

