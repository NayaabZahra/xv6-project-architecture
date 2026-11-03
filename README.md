# XV6 RISC-V Kernel Extension: Computer Architecture Project

## Project Overview
This project focuses on RISC-V processor architecture concepts and low-level hardware interactions by extending the MIT `xv6-riscv` kernel. It introduces diagnostic modules to inspect registers, traps, virtual memory mapping, interrupts, and memory-mapped I/O.

- **Base Kernel:** MIT xv6-riscv
- **Development Environment:** Windows (Host) / QEMU Emulator with RISC-V Toolchain
- **Group Size:** 3 Members

---

## Implemented / Proposed Modules

### Module 1: RISC-V Register Monitoring and Context-Switch Analysis
* **Objective:** Provide visibility into processor register states during execution and context switching.
* **Components:** 
  1. Register State Inspector
  2. Context-Switch Monitor
  3. Saved Context Analyzer
  4. Register Reporting Interface
  5. Debugging System Call
* **Working Mechanism:** Parses saved register values from process trap frames (`struct trapframe`) and context blocks (`struct context`) to trace states across context switches.

### Module 2: Advanced Trap and Exception Classification
* **Objective:** Improve monitoring, classification, and statistical logging of processor traps and exceptions.
* **Components:** 
  1. Trap Event Collector
  2. Exception Classification Engine
  3. Trap Cause Analyzer
  4. Event Statistics Manager
  5. Trap Reporting Interface
* **Working Mechanism:** Inspects the RISC-V `scause` CSR during traps to classify events (e.g., system calls, page faults, illegal instructions) and maintain diagnostic counters.

### Module 3: Sv39 Virtual Memory Translation Analyzer
* **Objective:** Inspect and demonstrate how RISC-V virtual addresses map to physical frames via Sv39 paging.
* **Components:** 
  1. Virtual Address Analyzer
  2. Page Table Inspector
  3. Page Table Entry Reader
  4. Address Translation Analyzer
  5. Translation Reporting Interface
* **Working Mechanism:** Traverses kernel multi-level page tables (`pagetable_t`), translating virtual page numbers (VPN) to physical page numbers (PPN) and evaluating page permission bits.

### Module 4: Interrupt Monitoring and Analysis
* **Objective:** Monitor and analyze timer and external hardware interrupts managed by the PLIC.
* **Components:** 
  1. Interrupt Event Collector
  2. Timer Interrupt Monitor
  3. External Interrupt Monitor
  4. Interrupt Statistics Manager
  5. Interrupt Reporting Interface
* **Working Mechanism:** Hooks into hardware interrupt handlers to count occurrences, measure handling latencies, and track interrupt sources.

### Module 5: Memory-Mapped I/O and VirtIO Device Monitoring
* **Objective:** Inspect communication between the operating system and virtual hardware devices using MMIO.
* **Components:** 
  1. Device Operation Monitor
  2. Memory-Mapped I/O Inspector
  3. VirtIO Request Tracker
  4. Device Event Collector
  5. I/O Statistics Interface
* **Working Mechanism:** Intercepts block I/O requests directed to VirtIO mmio register regions, tracking transaction status and storage throughput.

---

## Group Contributions
* **Member 3:** Architecture Analysis Lead (Modules 1 through 5: Registers, Traps, Sv39, Interrupts, and VirtIO MMIO)
* **Members 1 & 2:** Kernel environment setup, testing framework, and cross-project verification.

