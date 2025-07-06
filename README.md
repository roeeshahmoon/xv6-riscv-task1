# Operating Systems Assignment 1 — Processes and Scheduling

## Overview

This project contains my solutions for Assignment 1 in the Operating Systems course (Spring 2025, BGU). The tasks were completed using the xv6-riscv operating system, running under QEMU. The assignment covers processes, system calls, process memory management, and process scheduling in xv6.

## Assignment Structure

- **Task 0: Compiling and Running xv6**\
  Setup and compilation instructions for xv6 in a development container using Docker and VS Code.\
  *(No code submission for this task.)*

- **Task 1: Hello World**\
  Implementation of a userspace program (`helloworld.c`) that prints "Hello World xv6" inside xv6. Includes Makefile modification to add the new program.

- **Task 2: Kernelspace and System Calls**\
  Implementation of a new system call `memsize` that returns the memory usage (in bytes) of the current process. Includes a userspace program (`memsize_test.c`) to test this system call by checking memory usage before and after allocating/freeing memory.

- **Task 3: Goodbye World**\
  Extension of the process termination (exit) to accept and save an exit message in the PCB, and modification of the wait system call and the shell to print this message when a process ends. Includes a userspace program (`goodbye.c`) that exits with the message “Goodbye World xv6”.

- **Task 4: Distributing Work by Forking**\
  Implementation of two new system calls:

  - `forkn` — creates multiple child processes at once.
  - `waitall` — waits for all child processes to terminate and collects their exit statuses. Includes a userspace program (`bigarray.c`) that splits a large array into four parts, sums each part in a separate process, and prints the total sum in the parent.

## How to Build and Run

1. **Clone the xv6 repository (or use the provided xv6 source).**
2. **Open the project in VS Code using the Dev Containers extension.**
3. **Build and run xv6:**
   ```sh
   make qemu
   ```
4. **Test the new userspace programs from the xv6 shell:**
   - `helloworld`
   - `memsize_test`
   - `goodbye`
   - `bigarray`

## Files Submitted

- `helloworld.c` (user program)
- `memsize_test.c` (user program)
- `goodbye.c` (user program)
- `bigarray.c` (user program)
- Modified OS/kernel files:
  - `Makefile`
  - `syscall.h`, `syscall.c`
  - `sysproc.c`
  - `usys.pl`, `user.h`
  - `proc.h`, `proc.c`
  - `sh.c`
  - Any additional files as required by the tasks

## Additional Notes

- All tasks were implemented in a single xv6 copy as requested.
- Theoretical questions from the assignment are not included in this submission.
- Please see code comments for further explanations where relevant.

