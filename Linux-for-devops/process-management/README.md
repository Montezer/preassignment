## Process Management

When you start a program or application in Linux, it runs as a **process**.

A process can run in the foreground or background and uses system resources such as CPU and memory.

Each process is given a unique number called a **Process ID**, or **PID**.

## Common Process Management Commands

| Command | Description |
|---|---|
| `ps -ef` | Display all running processes in full detail |
| `ps aux` | Display detailed information about all running processes |
| `top` | View running processes and system resource usage in real time |
| `htop` | View processes using a more interactive interface |
| `kill <PID>` | Ask a process to stop normally |
| `kill -9 <PID>` | Force a process to stop immediately |
| `jobs` | Display jobs started from the current terminal |
| `bg` | Continue a suspended job in the background |
| `fg` | Bring a background or suspended job into the foreground |
| `command &` | Start a command in the background |
| `pgrep <process-name>` | Find the PID of a process by its name |
| `pkill <process-name>` | Stop processes using their name |

## Viewing Running Processes

### Using `ps -ef`

```bash
ps -ef
```

This displays all running processes.

Some important columns include:

| Column | Meaning |
|---|---|
| `UID` | User who started the process |
| `PID` | Process ID |
| `PPID` | Parent Process ID |
| `CMD` | Command that started the process |

### Searching for a Specific Process

You can combine `ps` with `grep`:

```bash
ps -ef | grep nginx
```

This searches the process list for processes containing the word `nginx`.

You can also use:

```bash
pgrep nginx
```

To display the process name and PID:

```bash
pgrep -a nginx
```

## Monitoring Processes with `top`

```bash
top
```

The `top` command displays running processes and updates the information continuously.

It shows information such as:

- CPU usage
- Memory usage
- Process IDs
- Running time
- Commands being executed

Press `q` to exit `top`.

> `top` does not only display the top 20 processes. It continuously displays processes and normally sorts them by CPU usage.

## Using `htop`

`htop` is an easier-to-read and more interactive alternative to `top`.

Install it on Ubuntu using:

```bash
sudo apt update
sudo apt install htop
```

Run it using:

```bash
htop
```

You can use the arrow keys to move through the process list and press `F10` to exit.

## Stopping a Process

Before stopping a process, find its PID:

```bash
ps -ef | grep nginx
```

Example output:

```text
root       1250       1  0 10:00 ?        00:00:00 nginx
```

In this example, the PID is `1250`.

### Stop the Process Normally

```bash
kill 1250
```

By default, `kill` sends the `SIGTERM` signal.

This asks the process to shut down cleanly and gives it an opportunity to save data and release resources.

You can write the signal explicitly:

```bash
kill -15 1250
```

### Force the Process to Stop

```bash
kill -9 1250
```

This sends the `SIGKILL` signal and immediately stops the process.

> Use `kill -9` only when the normal `kill` command does not work. It does not allow the process to clean up or save its current work.

## Running a Process in the Background

Add `&` to the end of a command:

```bash
sleep 100 &
```

This starts the command in the background and allows you to continue using the terminal.

To see background jobs started from the current terminal:

```bash
jobs
```

Example output:

```text
[1]+  Running    sleep 100 &
```

## Suspending a Foreground Process

While a command is running in the foreground, press:

```text
Ctrl + Z
```

This suspends the process.

You can then view it using:

```bash
jobs
```

## Continuing a Job in the Background

```bash
bg
```

To specify a particular job:

```bash
bg %1
```

This continues job number `1` in the background.

## Bringing a Job into the Foreground

```bash
fg
```

To bring a particular job into the foreground:

```bash
fg %1
```

## Process ID vs Job Number

A **PID** identifies a process across the operating system.

A **job number** identifies a command started from your current terminal session.

Examples:

```bash
kill 1250
```

Here, `1250` is a PID.

```bash
fg %1
```

Here, `%1` refers to job number `1`.

## Useful Example

Start a command in the background:

```bash
sleep 300 &
```

View the job:

```bash
jobs
```

Find its PID:

```bash
pgrep -a sleep
```

Stop it normally:

```bash
kill <PID>
```

Check whether it is still running:

```bash
pgrep -a sleep
```

## Managing Services vs Processes

A service is also made up of one or more processes, but services should normally be managed using `systemctl`.

For example, instead of finding and killing the Nginx process manually:

```bash
sudo systemctl stop nginx
```

This is safer than:

```bash
kill -9 <nginx-PID>
```

Use `systemctl` for managed services and process commands such as `ps`, `top` and `kill` for general process investigation and troubleshooting.