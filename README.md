# Hardware-Accelerated KNN Classifier on FPGA

## Overview
Real-time K-Nearest Neighbour (KNN) classifier implemented in pure RTL on ZedBoard FPGA for edge AI inference.

## Features
- ✅ 3D feature vector classification (X, Y, Z)
- ✅ 6 training samples stored in BRAM
- ✅ Configurable K (3 or 5) via hardware switch
- ✅ Pure RTL implementation (no floating-point)
- ✅ UART interface for input/output
- ✅ Low latency (<10 microseconds)
- ✅ Minimal resource usage (<5% of FPGA)

## Hardware Specifications
- **Device:** Xilinx xc7z020clg484-1 (ZedBoard)
- **Clock Frequency:** 100 MHz
- **Data Format:** 8-bit signed fixed-point
- **Interface:** UART 9600 baud

## Project Structure
KNN-FPGA-Classifier/
│
├── README.md                 # Project documentation
├── .gitignore               # Files to ignore
│
├── src/                     # Source files
│   ├── knn_top.v
│   ├── control_fsm.v
│   ├── Dataset.v
│   ├── distance_unit.v
│   ├── knn_selector.v
│   ├── majority_vote.v
│   ├── latency_counter.v
│   ├── uart_tx.v
│   ├── data_memory.v
│   └── dataset_memory.v
│
├── constraints/             # XDC files
│   └── zedboard.xdc
│
├── docs/                    # Documentation
│   ├── block_diagram.png
│   └── presentation.pdf
│
└── simulation/              # Testbenches (if any)
    └── knn_tb.v

## How to Use
1. Open project in Vivado
2. Generate bitstream
3. Program ZedBoard
4. Connect via UART (9600 baud)
5. Input format: `X Y Z K`
6. Output: Predicted class

## Performance
- **Latency:** <1 microsecond
- **LUT Usage:** 5.35%
- **Power:** Optimized for embedded

## Authors
[Your Name/Team Name]

## License
MIT License
