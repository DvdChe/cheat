# Signals system

Quick reference of common Unix/Linux signals and their purpose.

## Signal list with purpose

| Signal | #  | Purpose |
|--------|----|--------|
| HUP    | 1  | **Hangup** — Terminal disconnected, or sent to daemons to reload config (e.g. `kill -HUP nginx`) |
| INT    | 2  | **Interrupt** — User interrupt, typically Ctrl+C; request to stop |
| QUIT   | 3  | **Quit** — User quit; process should exit and optionally dump core |
| ILL    | 4  | **Illegal instruction** — CPU executed an invalid or privileged instruction |
| TRAP   | 5  | **Trace/breakpoint trap** — Debugger breakpoint or trace hit |
| ABRT   | 6  | **Abort** — Process called `abort()`; abnormal termination |
| EMT    | 7  | **Emulator trap** — Emulator trap (platform-specific) |
| FPE    | 8  | **Floating-point exception** — Erroneous arithmetic (e.g. division by zero) |
| KILL   | 9  | **Kill** — Unconditional termination; cannot be caught or ignored |
| BUS    | 10 | **Bus error** — Invalid memory access (misaligned or non-existent address) |
| SEGV   | 11 | **Segmentation violation** — Invalid memory reference (e.g. null pointer, bad address) |
| SYS    | 12 | **Bad system call** — Invalid or unimplemented system call |
| PIPE   | 13 | **Broken pipe** — Write to a pipe/socket with no readers (e.g. `cmd | head`) |
| ALRM   | 14 | **Alarm** — Timer expired (from `alarm()`); often used for timeouts |
| TERM   | 15 | **Termination** — Request to terminate gracefully (default of `kill`) |
| URG    | 16 | **Urgent** — Urgent/out-of-band data on a socket (rarely used) |
| STOP   | 17 | **Stop** — Pause process; cannot be caught or ignored |
| TSTP   | 18 | **Terminal stop** — User stop, typically Ctrl+Z; can be caught |
| CONT   | 19 | **Continue** — Resume a process stopped by STOP or TSTP |
| CHLD   | 20 | **Child** — Child process state changed (exited or stopped) |
| TTIN   | 21 | **Background read** — Background process tried to read from controlling tty |
| TTOU   | 22 | **Background write** — Background process tried to write to controlling tty |
| IO     | 23 | **I/O possible** — Pollable I/O event (e.g. `select()`/`poll()` ready) |
| XCPU   | 24 | **CPU time limit exceeded** — Process exceeded CPU time limit (e.g. setrlimit) |
| XFSZ   | 25 | **File size limit exceeded** — File grew beyond size limit |
| VTALRM | 26 | **Virtual alarm** — Virtual timer expired (e.g. `setitimer()` ITIMER_VIRTUAL) |
| PROF   | 27 | **Profiling timer** — Profiling timer expired (e.g. ITIMER_PROF) |
| WINCH  | 28 | **Window size change** — Terminal window resized |
| INFO   | 29 | **Information request** — Request for status (BSD; often unused) |
| USR1   | 30 | **User-defined 1** — Application-defined (e.g. reopen logs, reload) |
| USR2   | 31 | **User-defined 2** — Application-defined (e.g. graceful upgrade) |

> **Note:** Signal numbers can differ between systems (e.g. BSD vs Linux). Names are portable; use `kill -l` on your system to see the local mapping.
