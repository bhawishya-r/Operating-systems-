````md
# Processes and Threads

## 1. Process

A **process** is a program that is currently running.

When a program starts, the OS creates a process for it and manages its resources.

```text
Program
   ↓
Running
   ↓
Process
````

A process has its own resources, such as memory and execution state.

---

## 2. Multiprocessing

**Multiprocessing** means using multiple CPU cores to execute multiple processes in parallel.

```text
CPU
├── Core 1 → Process 1
├── Core 2 → Process 2
├── Core 3 → Process 3
└── Core 4 → Process 4
```

### Main benefit

> Multiple processes can execute at the same time using different CPU cores.

---

## 3. Thread

A **thread** is a unit of execution inside a process.

A process can contain multiple threads.

```text
Process
├── Thread 1
├── Thread 2
└── Thread 3
```

Threads within the same process share the process's resources, especially its memory.

---

## 4. Multithreading

**Multithreading** means having multiple threads running within the same process.

For example:

```text
Browser Process
├── UI Thread
├── Network Thread
└── Rendering Thread
```

Each thread can handle a different part of the program's work.

### Main benefit

> A program can perform multiple tasks concurrently without creating separate processes for each task.

---

## 5. Ryzen 5 3400G Example

The **Ryzen 5 3400G** has:

```text
4 Physical Cores
8 Hardware Threads
```

This means each physical core supports **2 hardware threads** through SMT.

```text
Ryzen 5 3400G
│
├── Core 1 → 2 Hardware Threads
├── Core 2 → 2 Hardware Threads
├── Core 3 → 2 Hardware Threads
└── Core 4 → 2 Hardware Threads
                  ↓
            8 Hardware Threads
```

So:

> **4 cores ≠ 8 physical cores.**

The CPU has **4 physical cores**, while the OS sees **8 logical processors**.

These hardware threads allow the CPU to keep its execution resources better utilized, but they do not provide the same performance as 8 separate physical cores.

---

## Quick Mental Model

```text
Program
   ↓
Process
   ↓
Threads
   ↓
CPU Hardware Threads
   ↓
CPU Cores
```

### In short

* **Process** → A running program.
* **Multiprocessing** → Multiple processes can execute in parallel.
* **Thread** → An execution unit inside a process.
* **Multithreading** → Multiple threads execute within one process.
* **Ryzen 5 3400G** → 4 physical cores + 8 hardware threads.
