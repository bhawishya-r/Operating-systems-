````md
# Types of Operating Systems

Operating systems can be classified based on how they execute and manage jobs, processes, CPU time, and computer systems.

---

## 1. Single-Process Operating System

A **Single-Process OS** executes one process at a time.

```text
P1 → Finish → P2 → Finish → P3
````

The next process starts only after the current process finishes.

 Limitation

If the current process is waiting for I/O, the CPU may remain idle.

```text
P1 → Waiting for I/O
          ↓
      CPU idle
```

---

 2. Batch Processing Operating System

A **Batch Processing OS** groups similar jobs into batches and executes them sequentially without requiring continuous user interaction.

```text
Batch
 │
 ├── Job 1
 ├── Job 2
 ├── Job 3
 └── Job 4
       ↓
   Execute in order
```

 Example

Large numbers of payroll calculations or data-processing jobs can be collected and executed as a batch.

### Limitation

The CPU can still remain idle when the current job is waiting for I/O.

---

 3. Multiprogramming Operating System

A **Multiprogramming OS** keeps multiple programs in memory and switches to another program when the current one cannot continue, such as when it is waiting for I/O.

The main goal is:

> **Maximum CPU utilization.**

```text
P1 → Waiting
       ↓
      P2 → P3
```

Instead of:

```text
P1 → Waiting
       ↓
   CPU idle ❌
```

the OS uses another available process.

 Context Switching

When switching between processes, the OS saves the current process state and loads another process's state.

The information required to resume a process is maintained in its:

**PCB = Process Control Block**

```text
P1
 ↓
Save context → PCB 1
 ↓
Load context from PCB 2
 ↓
P2
```

---

 4. Multitasking Operating System

A **Multitasking OS** allows multiple processes to share CPU time.

The CPU gives a process a specific amount of time, called a **time slice**, and then switches to another process.

```text
Time →

P1 | P2 | P3 | P1 | P2 | P3 |
```

Because switching happens very quickly, the user experiences multiple programs as running together.

 Priority

Processes can have different priorities.

A higher-priority process may be scheduled before a lower-priority process, depending on the scheduling policy.

 Example

**CTSS (Compatible Time-Sharing System)** is an important historical example of a time-sharing system.

---

 5. Distributed Operating System

A **Distributed OS** works across multiple autonomous computers that are interconnected through a network.

```text
Computer 1 ──┐
Computer 2 ──┼── Network
Computer 3 ──┘
```

The connected systems cooperate and work together as a distributed computing environment.

 Example

**Amoeba**

---

 6. Real-Time Operating System (RTOS)

A **Real-Time Operating System** is designed for systems where tasks must respond within specific timing requirements.

The important feature is not simply speed.

The important feature is:

> **Predictable and timely response.**

```text
Input
  ↓
RTOS
  ↓
Required response within deadline
  ↓
Output
```

Missing an important deadline can cause the system to fail or behave incorrectly.

 Examples / Uses

RTOSs are commonly used in:

* Embedded systems
* Robotics
* Industrial control systems
* Automotive systems
* Medical devices
* Aerospace systems

---

# Quick Comparison

| Type                | Main Idea                                | Example                       |
| ------------------- | ---------------------------------------- | ----------------------------- |
| Single Process OS   | One process at a time                    | Early/simple computer systems |
| Batch Processing OS | Jobs grouped and executed sequentially   | Payroll/data processing       |
| Multiprogramming OS | Switch to another process when one waits | Mainframe systems             |
| Multitasking OS     | Share CPU time between processes         | CTSS                          |
| Distributed OS      | Multiple networked computers cooperate   | Amoeba                        |
| RTOS                | Meet specific timing requirements        | Embedded/industrial systems   |

