# NodeX

A powerful, extensible command-line shell written in Python.

NodeX combines features from traditional shells (like Bash/PowerShell) with a plugin system, custom commands, and a modern, color-capable interface. It is designed for developers who want flexibility and control inside a Python-driven environment.

---

## Features

- Colorized output (ANSI + Minecraft-style `&` codes)
- Built-in command system (files, system, utilities)
- Plugin architecture for extending functionality
- Command history, aliases, and variables
- Background jobs (`&`, `jobs`, `fg`, `bg`)
- Pipes and redirection (`|`, `>`, `>>`)
- Built-in text editor (nano-like)
- HTTP tools (`curl`, `acurl`)
- Archive utilities (zip / unzip)
- Python integration (`pip`, `py`)
- Cross-platform support

---

## Installation

```bash
git clone https://github.com/your-username/nodex.git
cd nodex
python test.py
```

**Requirements:** Python 3.9+

---

## Usage

Start the shell:

```bash
python test.py
```

You will enter the interactive NodeX environment.

---

## Examples

```bash
help
ls -la
cd folder
echo &aHello
calc 2+2*10
grep text file.txt
download https://example.com/file
```

---

## Colors

NodeX supports Minecraft-style color codes:

```
&a  green
&c  red
&l  bold
&r  reset
```

Example:

```bash
echo &aSuccess!
```

---

## Plugins

Plugins are loaded automatically from:

```
/plugins
```

Example plugin:

```python
from nodex import command

@command("hello", "Say hello")
def hello(console, args):
    console.print_line("Hello, world!")
```

---

## Configuration

Configuration files are stored in:

```
~/.nodex/config.json
~/.nodex/aliases.json
~/.nodex/history.json
~/.nodex/variables.json
```

---

## Project Structure

```
core/        # core logic
ui/          # interface
plugins/     # extensions
test.py      # entry point
```

---

## Development Notes

- Safe evaluation for math expressions
- UTF-8 support
- Logging system
- Autocompletion via readline
- Customizable prompt

---

## License

MIT License

---

## Author

Link_314
