# Desktop Binary Analysis Guide

Guide for benign static analysis and architectural understanding of compiled binaries (ELF, PE, Mach-O).

## Static Identification Checklist

- File Format: Run `file <target>` to determine architecture (x86, x64, ARM), linking type (static vs dynamic), and strip status.
- Header Inspection:
  - Linux/ELF: `readelf -h <target>`, `readelf -d <target>` (dynamic section).
  - Windows/PE: Inspect PE headers, imports table, exports table via tools like PE-bear or dumpbin.
  - Dependencies: Use `ldd <target>` on Linux or Dependencies / Dependency Walker on Windows to trace linked shared libraries.
- String Extraction: Run `strings -a -n 8 <target>` to locate embedded URLs, error logs, library version identifiers, and internal function names.

## Disassembly and Decompilation

- Ghidra / Radare2: Load binary for architectural decompilation.
- Symbol Analysis: Locate the `main` or entry function. Inspect exported functions in DLLs/shared objects to document the API surface.
- Packing Detection: Check section entropy and common packer signatures (UPX, ASPack) before deep analysis.
