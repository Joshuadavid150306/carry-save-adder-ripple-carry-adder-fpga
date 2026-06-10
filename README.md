# Carry Select Adder (CSLA) Using Ripple Carry Adder on FPGA

## Overview

This project presents the design and FPGA implementation of a Carry Select Adder (CSLA) based on Ripple Carry Adder (RCA) architecture using Verilog HDL.

The Carry Select Adder improves computational speed by generating results for multiple carry conditions in parallel and selecting the appropriate output through multiplexing logic. This architecture significantly reduces carry propagation delay compared to conventional Ripple Carry Adders, making it suitable for high-performance arithmetic circuits.

---

## Key Features

- Modular Verilog HDL implementation
- FPGA-ready architecture
- Reduced propagation delay
- Hierarchical design methodology
- Functional simulation and verification
- Timing and resource utilization analysis
- Scalable architecture for wider bit-widths

---

## System Architecture

The design consists of:

1. Full Adder modules
2. Ripple Carry Adder blocks
3. Parallel carry computation paths
4. Multiplexer-based carry selection logic
5. FPGA implementation layer

### Architecture Flow

Input A, B
       │
       ▼
 ┌─────────────┐
 │ RCA (Cin=0) │
 └─────────────┘
       │
       │
 ┌─────────────┐
 │ RCA (Cin=1) │
 └─────────────┘
       │
       ▼
 ┌─────────────┐
 │ Multiplexer │
 └─────────────┘
       │
       ▼
   Sum & Cout

---

## Project Structure

carry-select-adder-fpga/

├── src/
│   ├── full_adder.v
│   ├── ripple_carry_adder.v
│   └── carry_select_adder.v
│
├── testbench/
│   └── csla_tb.v
│
├── constraints/
│   └── fpga_constraints.xdc
│
├── docs/
│   ├── architecture_diagram.png
│   ├── timing_report.pdf
│   └── project_report.pdf
│
├── results/
│   ├── simulation_waveform.png
│   ├── synthesis_report.pdf
│   └── fpga_output.jpg
│
├── README.md
├── LICENSE
└── .gitignore

---

## Design Methodology

### Step 1: Full Adder Design

A single-bit Full Adder is designed as the fundamental arithmetic building block.

### Step 2: Ripple Carry Adder Construction

Multiple Full Adders are cascaded to construct Ripple Carry Adders.

### Step 3: Carry Select Architecture

Two RCA blocks operate simultaneously:

- RCA assuming Carry-In = 0
- RCA assuming Carry-In = 1

### Step 4: Multiplexer Selection

The actual carry input selects the appropriate precomputed result.

### Step 5: FPGA Validation

The design is synthesized, implemented, and tested on FPGA hardware.

---

## Simulation Results

The design was verified through functional simulation to ensure:

- Correct Sum generation
- Correct Carry propagation
- Proper multiplexer selection
- Stable operation across test vectors

---

## Performance Analysis

| Parameter | RCA | CSLA |
|------------|------|------|
| Speed | Lower | Higher |
| Delay | High | Reduced |
| Area | Smaller | Slightly Larger |
| Throughput | Moderate | High |

---

## Applications

- Arithmetic Logic Units (ALUs)
- Digital Signal Processors
- FPGA Accelerators
- High-Speed Computing Systems
- Embedded Arithmetic Units
- Processor Datapaths

---

## Tools and Technologies

- Verilog HDL
- Xilinx Vivado
- ModelSim
- FPGA Development Board
- Digital Logic Design

---

## Future Scope

- Square Root CSLA implementation
- Low-power optimization techniques
- Pipelined architecture
- 16-bit, 32-bit, and 64-bit extensions
- ASIC implementation and comparison

---

## Author

Joshua

---

## License

This project is released under the MIT License.
