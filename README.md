#  Synchronous Dual-Priority FIFO

## 📌 Overview
This project implements a **Synchronous Dual-Priority FIFO** in Verilog with support for **independent high-priority (HP) and low-priority (LP) channels**.  
The FIFO ensures that **high-priority data is always served before low-priority data** during read operations.  

It includes **overflow and underflow protection**, preventing invalid writes when the FIFO is full and invalid reads when empty.  

The design is **parameterized** for flexible **data width** and **FIFO depth**, making it reusable across different applications.  

---

## ✨ Features
- ✅ **Dual-priority channels**: Separate high and low priority inputs  
- ✅ **Priority handling**: HP always has precedence over LP during reads  
- ✅ **Full/Empty protection**: Prevents data corruption on overflow/underflow  
- ✅ **Parameterizable design**: Configurable `DATA_WIDTH` and `DEPTH`  
- ✅ **Synchronous operation**: Single clock domain for reliable design  
- ✅ **Testbench validated**: Comprehensive test cases for verification  

---

## 📐 Design Parameters
```verilog
parameter DATA_WIDTH = 8;   // Width of each FIFO entry
parameter DEPTH      = 16;  // Number of entries in FIFO
parameter ADDR_WIDTH = 4;   // log2(DEPTH)

Verification
A self-checking testbench is included to validate functionality:
✅ Write/read operations for HP and LP channels
✅ Priority check (HP > LP on read)
✅ Full/empty protection validation
✅ Corner cases (simultaneous read/write, reset conditions)


