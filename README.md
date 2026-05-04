```markdown
<p align="center">
  <img src="https://img.shields.io/badge/NodeX-3.2.0--power-blue?style=flat-square&logo=python&logoColor=white" alt="Version"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" alt="License"/>
  <img src="https://img.shields.io/badge/Python-3.6%2B-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Platform-Windows%20|%20Linux%20|%20macOS-lightgrey?style=flat-square" alt="Platform"/>
</p>

<h1 align="center">
  NodeX
  <br>
  <sub>The next‑gen terminal you've been waiting for</sub>
</h1>

<p align="center">
  <b>NodeX</b> is a powerful, cross‑platform shell with a built‑in editor, games, process control, pipeline support, and an elegant color engine.<br>
  Perfect for developers, sysadmins, and anyone who wants a more capable command line.
</p>

<br>

## ✨ Features at a glance

| Category | What you get |
|----------|---------------|
| 🎨 **Colors** | Minecraft‑style codes (`&a`, `&c`, `&l`) – color any output |
| 📁 **File magic** | `ls --icons --tree --git`, `cat`, `grep`, `find`, `head`, `tail`, `tree`, `cp`, `mv`, `rm -r` |
| ✏️ **Built‑in editor** | Full‑screen `nano`‑like editor with line numbers, cross‑platform (Windows/Unix) |
| 🎮 **Games** | `snake` (Windows), `2048`, `guess` – inside your terminal |
| ⚙️ **System tools** | `ps`, `kill`, `ping`, `download`, `title`, `uptime` (psutil), `which` |
| 🔄 **Job control** | Background jobs (`&`), `jobs`, `fg`, `bg` – never block your prompt again |
| 🔗 **Pipes & redirection** | Complete pipeline support (`\|`, `>`, `>>`) |
| 🧩 **Plugin system** | Auto‑load Python scripts from `plugins/` – extend without forking |
| 🌐 **Multilingual** | Instant switch between English (`language en`) and Russian (`language ru`) |
| 📜 **Scripting** | `source` to run `.nodexrc` scripts, persistent aliases and variables |

<br>

## 🖥️ Quick preview

```
╔══════════════════════════════════════════════════════════════════════════╗
║                           NodeX | v.3.2.0-power                          ║
║          Power shell with job control, monitor, editor and plugins       ║
║                    help • neofetch • monitor • ls --icons                ║
║                       ⚡ NodeX elite mode enabled ⚡                      ║
╚══════════════════════════════════════════════════════════════════════════╝
[~/projects] $ ls --icons --git
  [DIR]  📁 .git/            [DIR]  📁 src/
  [PY ]  🐍 main.py          [CFG]  ⚙️ config.yaml
  [IMG]  🖼️ logo.png         [TXT]  📄 README.md
[~/projects] $ echo &aHello &lWorld!
Hello World!
```

<br>

## 🚀 Installation

**Requirements:** Python 3.6+ (3.10+ recommended) – optional but nice: `psutil` for `uptime`.

```bash
git clone https://github.com/yourusername/nodex.git
cd nodex

# (optional) virtual environment
python -m venv venv
source venv/bin/activate   # or .\venv\Scripts\activate on Windows

# optional dependency
pip install psutil

# run it
python test.py
```

> On first start, NodeX creates `~/.nodex/` with default configs.  
> Put your startup commands in `~/.nodexrc`.

<br>

## 📖 Command reference

### Essentials

| Command | Description |
|---------|-------------|
| `help` | Show complete help |
| `clear` | Clear screen + redraw banner |
| `exit` | Quit NodeX |
| `echo <text>` | Print with Minecraft color codes (`&aGreen`, `&cRed`) |
| `time` | Show current date/time |
| `calc <expr>` | Safe math evaluation |

### File operations

| Command | Description |
|---------|-------------|
| `ls [-a] [-l] [--icons] [--tree] [--git]` | List with icons, git status, tree view |
| `cd <dir>` | Change directory (`cd -` goes back) |
| `nano <file>` | Launch built‑in editor |
| `cat <file>` | Display file content |
| `grep <pattern> [file/dir]` | Search text (supports `--color`) |
| `find <name> [start_dir]` | Recursively find files by name |
| `tree [dir] [depth]` | Visual directory tree (default depth 3) |
| `mkdir`, `rm`, `mv`, `cp` | Standard file utils |

### System & processes

| Command | Description |
|---------|-------------|
| `ps` / `kill` | List / kill processes (`kill -f` for force) |
| `ping <host>` | ICMP ping test |
| `download <url> [filename]` | HTTP download |
| `title <text>` | Set terminal window title |
| `which <cmd>` | Locate executable in PATH |
| `uptime` | System uptime (needs psutil) |
| `sleep <seconds>` | Delay execution |
| `repeat <N> <command>` | Repeat a command N times |

### Customisation & environment

| Command | Description |
|---------|-------------|
| `alias [name=cmd]` / `unalias` | Manage command aliases |
| `set [var=value]` / `unset` | Shell variables (use as `$var`) |
| `export NAME=value` | Set environment variables |
| `prompt <template>` | Change prompt – supports `{cwd}`, `$var`, &-colors |
| `color <name>` | Change UI accent color (black, red, green, yellow, blue, magenta, cyan, white, etc.) |
| `language <ru\|en>` | Switch interface language |

### Job control & pipelines

| Command | Description |
|---------|-------------|
| `command &` | Run in background |
| `jobs` | List background jobs |
| `fg %jobid` | Bring job to foreground |
| `bg %jobid` | Resume background job |
| `cmd1 \| cmd2` | Pipe stdout to stdin |
| `cmd > file` or `cmd >> file` | Redirect output |

### Games

| Command | Description |
|---------|-------------|
| `guess` | Guess the number (1–100) |
| `snake` | Classic Snake (Windows only) |
| `2048` | 2048 puzzle (WASD / arrows) |

<br>

## 🧩 Plugins

Drop any Python file into the `plugins/` folder and NodeX will load it automatically.  
Your plugin can export a dictionary `PLUGIN_COMMANDS`:

```python
# plugins/weather.py
def weather(console, args):
    city = args[0] if args else "London"
    console.print_success(f"Weather in {city}: ☀️ 22°C")

PLUGIN_COMMANDS = {
    "weather": weather
}
```

Now `weather Paris` works immediately – no restart needed.

<br>

## 🎨 Color codes (Minecraft style)

Use `&` followed by a code anywhere text is printed (echo, prompt, etc.):

| Code | Color      | Code | Color         | Code | Effect       |
|------|------------|------|---------------|------|--------------|
| `&0` | black      | `&8` | dark gray     | `&l` | **bold**     |
| `&1` | dark blue  | `&9` | blue          | `&o` | *italic*     |
| `&2` | dark green | `&a` | green         | `&n` | <u>underline</u> |
| `&3` | dark aqua  | `&b` | aqua          | `&m` | ~~strike~~   |
| `&4` | dark red   | `&c` | red           | `&k` | blinking     |
| `&5` | purple     | `&d` | pink          | `&r` | reset        |
| `&6` | gold       | `&e` | yellow        |      |              |
| `&7` | gray       | `&f` | white         |      |              |

To print a literal `&`, prefix it with `*` → `echo *&a` outputs `&a`.

<br>

## 📂 Configuration

Everything lives in `~/.nodex/` (or `%USERPROFILE%\.nodex` on Windows):

| File | Purpose |
|------|---------|
| `config.json` | General settings (prompt, language, color, sandbox mode) |
| `aliases.json` | Custom aliases |
| `variables.json` | Persistent shell variables |
| `history.json` | Command history (last 200 entries) |
| `command_stats.json` | Usage frequency per command |
| `nodex.log` | Error log |

### Startup script: `~/.nodexrc`

NodeX runs every command from this file at launch. Example:

```
prompt &a[{cwd}] &d$> &r
alias ll="ls --icons --git --long"
export EDITOR=nano
```

<br>

## 🤝 Contributing

NodeX is MIT licensed. Contributions are welcome!

- Fork the repo
- Create a feature branch
- Commit your changes (PEP 8 + docstrings)
- Open a Pull Request

<br>

## 📄 License

MIT © 2025 **Veez_615**  
See [LICENSE](LICENSE) for details.

<br>

<p align="center">
  Made with ❤️ and Python<br>
  <sub>“Your terminal should work for you, not against you.”</sub>
</p>
```
