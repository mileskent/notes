---
date: 2026-06-26
---

The pipe operator `|` connects the stdout of one program to the stdin of the next, forming a pipeline:

```bash
cat log.txt | grep "error" | sort | uniq -c
```

Each `|` spawns a new [[Process]], and the [[Operating System]] manages a buffer between them. If the buffer fills, the writing process blocks until the reading process consumes some data. This is backpressure.

Only stdout is piped. Stderr still goes to the terminal unless explicitly redirected with `2>&1` before the pipe. See [[Redirect Operator]].

# Named Pipes (FIFOs)

A regular pipe is anonymous and exists only for the lifetime of the pipeline. A named pipe (FIFO) is a special file on disk that allows unrelated processes to communicate:

```bash
mkfifo my_pipe
program_a > my_pipe &
program_b < my_pipe
```

The FIFO blocks until both a reader and writer are connected. Data flows through the kernel buffer, not through the file on disk.

# xargs

Some programs don't read from stdin. `xargs` converts stdin into arguments:

```bash
# find outputs file paths on stdout, xargs passes them as arguments to rm
find . -name "*.tmp" | xargs rm
```

Without `xargs`, `rm` would ignore the piped input entirely because it expects arguments, not stdin.
