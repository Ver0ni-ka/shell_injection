# Windows Shellcode Injection (C++)

A simple educational implementation of a classic process injection technique using Windows API, developed as a practical task for a security course.

This program demonstrates how raw shellcode (generated using Metasploit via `msfvenom`) can be injected into a target process (`notepad.exe` in this case) and executed within its address space by creating a remote thread.

## How It Works
1. Find Target PID using `CreateToolhelp32Snapshot`.
2. Open Process with sufficient access rights (`PROCESS_ALL_ACCESS`).
3. Allocate Memory using `VirtualAllocEx` with `PAGE_EXECUTE_READWRITE` permissions.
4. Write Shellcode (payload) into the allocated memory space using `WriteProcessMemory`.
5. Execute: Spawns a remote thread pointing to the shellcode using `CreateRemoteThreadEx`.

---
*Disclaimer: This project is created strictly for educational purposes and cybersecurity research.*
