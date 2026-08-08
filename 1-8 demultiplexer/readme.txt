# 1×8 Demultiplexer Using Verilog

## Project Overview

This project implements a **1×8 Demultiplexer (DEMUX)** using Verilog HDL.

A 1×8 Demultiplexer is a combinational logic circuit with:

* **1 data input**
* **3 select lines**
* **8 outputs**

The three select lines determine which one of the eight outputs receives the input data.

## Inputs and Outputs

### Inputs

* `D` – Data input
* `S2` – Select line 2
* `S1` – Select line 1
* `S0` – Select line 0

### Outputs

* `Y0` – Output 0
* `Y1` – Output 1
* `Y2` – Output 2
* `Y3` – Output 3
* `Y4` – Output 4
* `Y5` – Output 5
* `Y6` – Output 6
* `Y7` – Output 7

## Block Diagram

```text
                         ┌─────────────────┐
                         │                 │─── Y0
                         │                 │─── Y1
                         │                 │─── Y2
        D ──────────────►│     1 × 8       │─── Y3
                         │  DEMULTIPLEXER  │─── Y4
       S2 ──────────────►│                 │─── Y5
       S1 ──────────────►│                 │─── Y6
       S0 ──────────────►│                 │─── Y7
                         └─────────────────┘
```

## Truth Table

| S2 | S1 | S0 | D | Y0 | Y1 | Y2 | Y3 | Y4 | Y5 | Y6 | Y7 |
| -- | -- | -- | - | -- | -- | -- | -- | -- | -- | -- | -- |
| 0  | 0  | 0  | D | D  | 0  | 0  | 0  | 0  | 0  | 0  | 0  |
| 0  | 0  | 1  | D | 0  | D  | 0  | 0  | 0  | 0  | 0  | 0  |
| 0  | 1  | 0  | D | 0  | 0  | D  | 0  | 0  | 0  | 0  | 0  |
| 0  | 1  | 1  | D | 0  | 0  | 0  | D  | 0  | 0  | 0  | 0  |
| 1  | 0  | 0  | D | 0  | 0  | 0  | 0  | D  | 0  | 0  | 0  |
| 1  | 0  | 1  | D | 0  | 0  | 0  | 0  | 0  | D  | 0  | 0  |
| 1  | 1  | 0  | D | 0  | 0  | 0  | 0  | 0  | 0  | D  | 0  |
| 1  | 1  | 1  | D | 0  | 0  | 0  | 0  | 0  | 0  | 0  | D  |

## Logic Equations

```text
Y0 = D & ~S2 & ~S1 & ~S0
Y1 = D & ~S2 & ~S1 &  S0
Y2 = D & ~S2 &  S1 & ~S0
Y3 = D & ~S2 &  S1 &  S0
Y4 = D &  S2 & ~S1 & ~S0
Y5 = D &  S2 & ~S1 &  S0
Y6 = D &  S2 &  S1 & ~S0
Y7 = D &  S2 &  S1 &  S0
```

## Project Files

```text
1x8-demultiplexer/
│
├── README.md
├── demux_1x8.v
├── demux_1x8_tb.v
│
└── output/
    └── simulation_output.txt
```

### `demux_1x8.v`

Contains the Verilog design code for the 1×8 Demultiplexer.

### `demux_1x8_tb.v`

Contains the testbench used to verify all eight select combinations.

### `output/simulation_output.txt`

Contains the simulation results.

## How to Run

Using Icarus Verilog:

```bash
iverilog -o demux_sim demux_1x8.v demux_1x8_tb.v
```

Run the simulation:

```bash
vvp demux_sim
```

## Applications

1×8 Demultiplexers are used in:

* Data routing
* Data distribution
* Digital communication
* Memory selection
* Control systems
* Computer architecture
* Digital logic circuits

## Conclusion

The Verilog implementation successfully routes a single input signal to one of eight outputs based on the three select lines.

The testbench verifies all eight possible select combinations and confirms that the correct output is activated.

## Author

**Verilog HDL Digital Logic Project**
