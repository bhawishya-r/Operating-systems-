# Introduction to Operating Systems

> An Operating System is the layer between **applications/users** and the **hardware** that makes the computer usable.

---

## 1. The Basic Idea

A computer has two major worlds:

```text
┌──────────────────────────────┐
│          USER                │
│   "I want to do something"   │
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│       APPLICATIONS           │
│ Browser │ Games │ VS Code    │
│ Media   │ Terminal │ etc.    │
└──────────────┬───────────────┘
               │
               ▼
┌══════════════════════════════┐
║      OPERATING SYSTEM        ║
║                              ║
║  Resource Management         ║
║  Memory Management            ║
║  Hardware Abstraction         ║
║  Protection & Isolation       ║
║  User Interface              ║
└──────────────┬───────────────┘
               │
               ▼
┌──────────────────────────────┐
│          HARDWARE            │
│ CPU │ RAM │ Disk │ GPU │ NIC │
└──────────────────────────────┘
```
---

An Operating System is a piece of software that manages the resources of a computer system and provides an environment in which users and programs can run efficiently, while hiding the underlying complexity of the hardware.

In simpler words:
```
OS = Manager + Interface + Protection Layer + Hardware Abstraction
```

Why Do We Need an OS?

Imagine there was no Operating System.

You wanted to open a program.
```
The program would somehow need to understand:
How do I use the CPU?
How do I access RAM?
How do I read data from the disk?
How do I communicate with the keyboard?
How do I send data through the network card?
How do I display something on the screen?
```
Every application would have to deal with these hardware details itself.

That would be extremely complicated.

Instead:
```
Application
     │
     │ "I need a resource"
     ▼
Operating System
     │
     │ manages the request
     ▼
Hardware
```
The OS hides much of this complexity.

This is one of the most important ideas behind Operating Systems:

Applications can work with abstractions instead of dealing directly with the raw hardware.

---

Major Roles of an Operating System

The OS performs several important jobs.
```
                 OPERATING SYSTEM
                        │
       ┌────────────────┼────────────────┐
       │                │                │
       ▼                ▼                ▼
 Resource           Memory          Interface
 Management        Management
       │                │                │
       ▼                ▼                ▼
 CPU / RAM /       RAM / Storage       GUI / CLI
 Devices
       
       ┌────────────────┼────────────────┐
       │                                 │
       ▼                                 ▼
 Protection &                    Hardware
 Isolation                       Abstraction
```
One Real-World Example

```
You
 │
 │ Click browser
 ▼
Operating System
 │
 ├── Creates/manages the process
 │
 ├── Allocates memory
 │
 ├── Gives CPU time
 │
 ├── Provides access to storage
 │
 ├── Provides network access
 │
 └── Displays output through hardware
      │
      ▼
    Hardware
```

---

Connection to Cybersecurity

Operating Systems are extremely important in cybersecurity.

Why?

Because attackers and defenders ultimately interact with a system's:
```
Processes
Memory
Files
Users
Permissions
Network
Services
Devices
System calls
```
Understanding the OS means understanding what is actually happening underneath applications.

For cybersecurity, the OS is therefore not just another subject.

It is one of the layers we eventually need to understand deeply.
