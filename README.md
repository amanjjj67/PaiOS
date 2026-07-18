# PaiOS

A tiny terminal-based operating system that runs entirely in your browser. No install, no backend, no dependencies — open one HTML file and you're at a prompt.

![status](https://img.shields.io/badge/status-active-brightgreen) ![type](https://img.shields.io/badge/type-single--file-blue) ![license](https://img.shields.io/badge/license-MIT-lightgrey)

## Live demo

Open `index.html` in any browser, or [enable GitHub Pages](#deploying-with-github-pages) to run it at a public URL.

## What it is

PaiOS simulates a boot sequence, a shell, and a filesystem — all in memory, all in a single `.html` file with no external libraries. It's built for the amber-on-black CRT aesthetic of a real terminal, scanlines included, and behaves like a small Unix-like shell:

- A boot sequence with a kernel-load animation and ASCII logo
- An in-memory virtual filesystem with directories and files
- Command history you can walk with the arrow keys
- File redirection (`echo "text" > file`, `>>` to append)

Nothing persists between page reloads — every session starts fresh, which keeps the whole thing self-contained and safe to run anywhere.

## Commands

| Command | Description |
|---|---|
| `help` | List available commands |
| `ls [path]` | List directory contents |
| `cd [path]` | Change directory |
| `pwd` | Print working directory |
| `cat <file>` | Print file contents |
| `echo <text>` | Print text |
| `echo <text> > file` | Write text to a file (overwrite) |
| `echo <text> >> file` | Append text to a file |
| `mkdir <name>` | Create a directory |
| `touch <name>` | Create an empty file |
| `rm <name>` | Remove a file or empty directory |
| `tree` | Show the filesystem tree from the current directory |
| `whoami` | Show the current user |
| `neofetch` | Show a system info banner |
| `date` | Show the current date and time |
| `history` | Show command history |
| `clear` | Clear the screen |
| `reboot` | Replay the boot sequence |

## Usage

```bash
git clone https://github.com/amanjjj67/PaiOS.git
cd PaiOS
```

Then just open `index.html` in your browser — double-click it, or drag it into a browser window.

## Deploying with GitHub Pages

1. Go to **Settings → Pages** in this repository
2. Under "Source," select branch `main` and folder `/ (root)`, then **Save**
3. GitHub will publish the site at `https://amanjjj67.github.io/PaiOS/` within a minute or two

## How it works

Everything lives in one file:

- **HTML/CSS** renders the terminal chrome — the CRT scanline overlay, the amber phosphor color scheme, and the flicker animation
- **JavaScript** implements a tiny shell: a command parser, an in-memory tree of directory/file objects standing in for a real filesystem, and handlers for each built-in command

There's no server and no storage — refreshing the page resets PaiOS to a clean boot.

## Roadmap ideas

- Persist the filesystem to `localStorage` between sessions
- Add a basic text editor command (`edit <file>`)
- Tab-completion for paths and commands
- Themeable color schemes (green phosphor, IBM blue, etc.)

## License

MIT — do whatever you'd like with it.
