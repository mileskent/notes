---
date: 2026-06-26
---

The redirect operator `>` connects a program's output to a file instead of the terminal. By default, a [[Process|process]] has three standard streams, each identified by a [[File Descriptor]]:

| FD  | Name   | Default  |
| --- | ------ | -------- |
| 0   | stdin  | keyboard |
| 1   | stdout | terminal |
| 2   | stderr | terminal |

# Operators

| Bash   | PowerShell     | Effect                                      |
| ------ | -------------- | ------------------------------------------- |
| `>`    | `>`            | Redirect stdout to file (overwrite)         |
| `>>`   | `>>`           | Redirect stdout to file (append)            |
| `<`    | Get-Content \| | Redirect file to stdin                      |
| `2>`   | `2>`           | Redirect stderr to file                     |
| `2>>`  | `2>>`          | Redirect stderr to file (append)            |
| `&>`   | `*>`           | Redirect both stdout and stderr to file     |
| `2>&1` | `2>&1`         | Redirect stderr to wherever stdout is going |
| `1>&2` | `1>&2`         | Redirect stdout to wherever stderr is going |

The number before `>` selects which file descriptor to redirect. `&` on the right side means "file descriptor", not "file named 1". So `2>&1` says "send FD 2 (stderr) to the same place as FD 1 (stdout)."

Without `&`, `2>1` would redirect stderr to a file literally named `1`.

# Combining with Pipes

A [[Pipe]] `|` only passes stdout to the next program. To also capture stderr through a pipe, redirect it into stdout first:

```bash
program 2>&1 | grep "error"
```

Order matters. The shell processes redirections left to right:
```bash
# stderr goes to stdout, then stdout goes to file
program > output.txt 2>&1    # file gets both stdout and stderr

# stdout goes to file, then stderr goes to original stdout (terminal)
program 2>&1 > output.txt    # file gets only stdout, stderr still on terminal
```

# Tee

`tee` reads from stdin and writes to both a file and stdout simultaneously, letting you save output while still seeing it.

```bash
# Capture both stdout and stderr to file, and still see it in the terminal
program 2>&1 | tee output.txt

# Append instead of overwrite
program 2>&1 | tee -a output.txt
```

```powershell
# Capture both stdout and stderr to file, and still see it in the terminal
program 2>&1 | Tee-Object -FilePath output.txt

# Append instead of overwrite
program 2>&1 | Tee-Object -FilePath output.txt -Append
```

# /dev/null

Redirect to `/dev/null` to silently discard output:
```bash
program > /dev/null 2>&1    # discard everything
program 2> /dev/null        # discard only errors
```
