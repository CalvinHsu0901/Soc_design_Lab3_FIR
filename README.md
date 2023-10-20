# Soc_design_Lab3_FIR
11-taps FIR with AXI-lite & AXI-streaming interfaces

## Specification
- Data_Width  32
- Tape_Num    11
- Data_Num    To be determined by data size
## Interface
-- data_in  stream （Xn）
-- data_out: stream ( Yn)
-- coef[Tape_Num-1:0]  axilite
-- len: axilite
-- ap_start:  axilite
-- ap_done: axilite
- Using one Multiplier and one Adder
- - Shift register implemented with SRAM (Shift_RAM, size = 10 DW) – size = 10 DW
- Tap coefficient implemented with SRAM (Tap_RAM = 11 DW) and initialized by axilite write
Operation
- ap_start to initiate FIR engine (ap_start valid for one clock cycle)
- Stream-in Xn. The rate is depending on the FIR processing speed. Use axi-stream valid/ready for flow control
- Stream out Yn, the output rate depends on FIR processing speed.

## Block Diagram:
FIR top:
![FIR top](FIR_top.png)

FIR ALU:
![FIR](FIR.jpg)

Tap RAM:
![Tap RAM](Tap_RAM.jpg)

Data RAM:
![Data RAM](Data_RAM.jpg)
