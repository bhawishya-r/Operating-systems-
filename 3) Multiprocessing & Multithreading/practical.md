**screenshots captured from my kali VM **
tool used for viewing processes : htop

<img width="1485" height="888" alt="htp-ss" src="https://github.com/user-attachments/assets/66af4a83-896c-468b-a7e1-fb324efd5564" />
```
PROCESS
│
├── Thread 1  ──┐
├── Thread 2    │
├── Thread 3    ├── share the process's resources
└── Thread 4  ──┘
```
The process is the container.

The threads are the workers doing execution inside that container.

A process has its own resources such as:
```
Virtual memory
File descriptors
Security contexts
Other OS-managed resource
```

Threads within that process share much of those resources, especially the same memory space, while each thread has its own execution state such as its stack and CPU registers.

<img width="1486" height="686" alt="cpu-ss" src="https://github.com/user-attachments/assets/91884323-c379-4cf4-b252-4154d0d1a261" />

basic information about Ryzen5 3400g 
we can see the architecture which is x84_64 , And CPU cores are 4.
