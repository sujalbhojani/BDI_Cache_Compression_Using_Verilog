# BDI_Cache_Compression_Using_Verilog
Base-Delta-Immediate Compression implementation for Cache using Verilog HDL

# Overview

The BDI Cache Compression technique leverages patterns found in memory data to compress cache lines by identifying a common base value and representing other values as small differences (deltas) from this base. The "Immediate" part refers to small constant values that can be stored directly without further compression.

This project implements the BDI algorithm in Verilog, simulating how BDI can be applied to cache lines to increase effective cache capacity.

# Features

- **Base-Delta Compression**: Compresses cache lines by identifying a base value and using delta encoding.
- **Immediate Value Handling**: Efficiently stores small constant values directly.
- **Verilog Implementation**: Pure hardware description, making it suitable for FPGA or ASIC designs.
- **Testbench**: Provided for validating the compression and decompression logic.
