# FPGA-Fabric_Design_and_Architecture
This document is a report of the intensive 5-day workshop organized by [VLSI System Design](https://www.vlsisystemdesign.com/).<br/>
As a gist, a 4-bit counter and RVMyth processor are taken as the units under test. These are processed on various OpenSource platforms (Basys3, VTR, and SOFA), and the results obtained on these platforms are compared from timing, power, and area point of view. Day-to-day gist of the workshop is given below:<br/>
- On day-1, a 4-bit counter is designed on Basys3 and the Virtual Input/Output (VIO) strobes of the results are demonstrated.<br/>
- On day-2, Verilog To Route (VTR) flow is explored with the 4-bit counter example and the results (timing, Power, and Area) of VTR and Basys3 are compared.<br/>
- On day-3, the processor code for RVMyth is studied and is run till bitstream on Basys3.<br/>
- On day-4, the timing, Power, and Area results of the 4-bit counter are studied on Skywater OpenSource FPGA (SOFA).<br/>
- On day-5, the RVMyth processor is studied on SOFA and the timing, power, and area results are noted.<br/>

The elaboration of these steps makes this document.<br/>

## Platforms used:
- xyz for doing 123
- pqr to study 234
- mno for analyzing 345
- jkl to 456

## Commands used
  ```
  - cmd1
  - cmd2
  - cmd3
  ```

# Day-wise contents of the workshop
  - Day1
    - [Introduction to FPGA]()
      - What is FPGA?
      - LUTs and ways for programming FPGAs
      - The Basys FPGA boards and Vivado
    - [Vivado_Counter]()
      - Verilog Simulation
      - A bit more on simulation
      - Map pins
      - Slack
      - Synthesis
      - Bitstream constraints
      - Bitstream generation view on Basys3
      - Timing
      - Power_Area
    - [VIO_Counter]()
      - Introduction
      - Code
      - Bitstream Outputs
  - Day2
    - [Introduction to OpenFPGA]()
      - Part-1
      - Part-2
      - VTR flow
    - [VPR]()
      - xml blif
      - tseng GUI
      - Timing report
    - [VTR]()
      - VTR flow with VPR GUI
      - Post synthesis simulation
      - Timing_Area
      - Power Analysis
    - [Earch and Basys3 result comparison]()
  - Day3
    - [RISC_V core programming using Vivado]()
      - RVMyth Vivado RTL to Synthesis
      - RVMyth Vivado Synthesis to bitstream
  - Day4
    - [Introduction to SOFA FPGA Fabric IP]() 
      - Counter Area
      - Counter Timing
      - Counter post impl
      - Counter Power
  - Day5
    - [RISC_V core on custom SOFA fabric]()
      - SOFA-RVMyth run
      - SOFA-RVMyth timing and area
      - RVMyth post impl netlist
      - SOFA-RVMyth Vivado simulation
