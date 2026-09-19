# 4) System Calls

## What are System Calls?

A **system call (syscall)** is the interface through which a user-space program requests services from the Linux kernel.

**Flow:**

`User Program → System Call → Linux Kernel → System Resource`

Examples include process management, file operations, memory management, networking, and IPC.

## Practical Experiment

Created and executed a Bash script containing an infinite loop:

```bash
#!/bin/bash

while true
do
    echo "An experiment"
    sleep 1
done
```

The script continuously prints `An experiment` with a 1-second delay.

### Tools Used

* Kali Linux
* Bash
* `strace`
* `htop`

## Screenshot Evidence

### 1. `bash-script.png`

Shows the Bash script itself, including the infinite loop, `echo`, and `sleep 1` commands.

### 2. `file-exc.png`

Shows the script actively executing. `An experiment!` is printed once every second, demonstrating the loop and the `sleep` operation.

### 3. `strace_capture.png`

Shows the system calls generated while executing the script. This connects the Bash-level commands with the underlying kernel interactions.

### 4. `process-sleep.png`

Shows the running process in `htop`, allowing observation of the script/process and its relationship with the `sleep` process.

## Key Learning

This experiment connected:

**Bash Script → Process → System Calls → Linux Kernel**

It helped visualize how a simple user-space script interacts with the operating system underneath.
