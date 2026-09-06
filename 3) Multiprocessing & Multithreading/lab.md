# Lab: Exploring Windows Processes, Threads, Handles & Registry

## Objective

Explore Windows OS internals using **Microsoft Sysinternals Process Explorer** and **Windows Registry Editor**.

The goal was to understand how Windows manages processes and threads, and how system/user configuration is organized in the Registry.

## Tools Used

- Windows
- Microsoft Sysinternals Process Explorer
- Windows Registry Editor

---

# 1. Exploring Processes

I opened **Process Explorer** to explore running processes in Windows.

I selected a `conhost.exe` process associated with `cmd.exe` and inspected its properties.

### What I observed

Process Explorer showed information such as:

- Process ID (PID)
- Parent process
- CPU usage
- Memory usage
- Handles
- Threads
- Process priority
- Other process information

<img width="484" height="627" alt="process" src="https://github.com/user-attachments/assets/8bb84b2f-934b-4c23-9a13-f6a2cc000d32" />




# 2. Exploring Threads

Inside the `conhost.exe` process, I opened the **Threads** section and inspected individual threads.

This allowed me to see information about how Windows manages each thread, including:

- Thread ID
- CPU usage
- Context switches
- I/O priority
- Memory priority
- Ideal processor

### Context Switching

The **context switch count** showed how frequently a thread had been switched between CPU execution and waiting/other execution states.

This helped connect the OS theory of **CPU scheduling and context switching** with an actual Windows process.

### Ideal Processor

The **ideal processor** indicates the logical processor that Windows considers preferable for scheduling that particular thread.

<img width="484" height="621" alt="thread" src="https://github.com/user-attachments/assets/fdc125e5-1c68-4b0e-b1d2-a4c317364fba" />


# 3. Exploring Windows Registry

I also explored the Windows Registry to understand how Windows organizes system and user configuration.

The main Registry root keys I explored were:

| Root Key | Purpose |
|---|---|
| `HKEY_LOCAL_MACHINE (HKLM)` | Machine-wide system and configuration information |
| `HKEY_CURRENT_USER (HKCU)` | Configuration for the currently logged-in user |
| `HKEY_CLASSES_ROOT (HKCR)` | File associations and class/COM registration information |
| `HKEY_CURRENT_CONFIG (HKCC)` | Information related to the current hardware configuration |

<img width="293" height="295" alt="image" src="https://github.com/user-attachments/assets/5e8cb677-1321-46f5-b638-eb59a22d6b4d" />


# 4. Registry Data Types

I explored some common Registry value types:

| Type | Description |
|---|---|
| `REG_SZ` | String/text value |
| `REG_DWORD` | 32-bit numeric value |
| `REG_BINARY` | Binary data |

These different data types allow applications and Windows components to store different kinds of configuration data.


# 5. Registry Configuration Experiment

I modified the **EULA-related Registry value** used by Process Explorer.

After changing the value, I launched Process Explorer again.

The application prompted me to accept the license agreement again.

This demonstrated that an application's behavior can depend on configuration values stored in the Windows Registry.

```text
Registry Value
      ↓
Application reads configuration
      ↓
Application behavior changes
```
<img width="333" height="199" alt="image" src="https://github.com/user-attachments/assets/270cc7c6-2a62-46fd-bf9e-1740b2a63529" />
