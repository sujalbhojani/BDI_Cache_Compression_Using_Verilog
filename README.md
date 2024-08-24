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

# Key Components:

- **Base Selection**:
  The base value for 8-byte, 4-byte, and 2-byte encoding is selected from the first chunk of data (e.g., Base8 = UnCompressedCache[63:0] for 8-byte).

- **Delta Calculation**:
  For each section of the data, deltas are computed by subtracting the base value from the corresponding data chunk.

- **Delta Encoding**:
  The code checks if the computed deltas can fit into smaller sizes (1 byte, 2 bytes, etc.).
  If they can, it sets a compression flag (CoN) and constructs the compressed cache line (CCL).

- **Compression Conditions**:
  Each delta is checked to see if the higher-order bits are all 0 or all 1. This check determines if the delta can be represented in fewer bits.
  If all deltas meet the conditions for a certain bit width, the compressed line is formed.
