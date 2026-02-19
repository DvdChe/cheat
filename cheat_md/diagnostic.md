# Quick machine health / incident diagnostics

Commands to run first when a machine is unhealthy. Run as root or with sudo when needed.

## CPU & load

```bash
# Load average (1/5/15 min), running vs blocked
uptime

# Per-CPU and overall usage, top processes
top -bn1 | head -20
# or: htop (if available)

# Quick CPU summary
mpstat 1 3
```

## Memory & OOM

```bash
# Free vs used, buffers/cache, swap
free -h

# OOM kills (kernel killed processes for low memory)
dmesg | grep -i "out of memory\|oom-killer\|killed process"
journalctl -k -b | grep -i "out of memory\|oom-killer\|killed process"

# Current memory usage by process
ps aux --sort=-%mem | head -20
```

## Disk & I/O

```bash
# Disk space (human-readable)
df -h

# Inode usage (can exhaust before space)
df -i

# I/O wait and disk stats (1s interval, 5 samples)
vmstat 1 5
iostat -x 1 3
```

## Processes & runaway

```bash
# Most CPU-heavy processes
ps aux --sort=-%cpu | head -15

# Count by state (R=run, S=sleep, D=uninterruptible, Z=zombie)
ps -eo state | sort | uniq -c

# Zombies
ps aux | grep Z
```

## Network

```bash
# Listen ports and established connections
ss -tulnp
ss -tn state established

# Per-process connections (e.g. find who uses port 80)
ss -tulnp | grep :80
```

## System & logs

```bash
# Last boot and recent reboots (crash?)
uptime
last reboot | head -5

# Recent kernel errors
dmesg -l err,crit,alert,emerg
journalctl -p err -b --no-pager | tail -50
```

## One-liner overview

```bash
echo "=== uptime ===" && uptime && echo "=== memory ===" && free -h && echo "=== disk ===" && df -h / && echo "=== top CPU ===" && ps aux --sort=-%cpu | head -6 && echo "=== top MEM ===" && ps aux --sort=-%mem | head -6 && echo "=== OOM? ===" && dmesg | grep -i "oom-killer\|killed process" | tail -5
```
