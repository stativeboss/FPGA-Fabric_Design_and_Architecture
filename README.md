# FPGA-Fabric_Design_and_Architecture
This document is a report of the 5-day intensive workshop on FPGAs, organized by [VLSI System Design](https://www.vlsisystemdesign.com/).<br/>
As a gist, a 4-bit counter and RVMyth processor are taken as the units under test. These are processed on various platforms (Basys3, VTR, and SOFA), and the results obtained on these platforms are compared from timing, power, and area point of view. Day-to-day gist of the workshop is given below:<br/>
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
    - <details>
      <summary> [Introduction to FPGA](#introduction-to-fpga) </summary>
  
      - What is an FPGA?
      - LUTs and ways for programming FPGAs
      - The Basys FPGA boards and Vivado
      </details>
    - [Vivado_Counter](#vivado_counter)
      - Verilog Simulation
      - A bit more on simulation
      - Map pins
      - Slack
      - Synthesis
      - Bitstream constraints
      - Bitstream generation view on Basys3
      - Timing
      - Power_Area
    - [VIO_Counter](#vio_counter)
      - Introduction
      - Code
      - Bitstream Outputs
  - Day2
    - [Introduction to OpenFPGA](#introduction-to-openfpga)
      - Part-1
      - Part-2
      - VTR flow
    - [VPR](#vpr)
      - xml blif
      - tseng GUI
      - Timing report
    - [VTR](#vtr)
      - VTR flow with VPR GUI
      - Post synthesis simulation
      - Timing_Area
      - Power Analysis
    - [Earch and Basys3 result comparison](#earch-and-basys3-result-comparison)
  - Day3
    - [RISC_V core programming using Vivado](#risc_v-core-programming-using-vivado)
      - RVMyth Vivado RTL to Synthesis
      - RVMyth Vivado Synthesis to bitstream
  - Day4
    - [Introduction to SOFA FPGA Fabric IP](#introduction-to-sofa-fpga-fabric) 
      - Counter Area
      - Counter Timing
      - Counter post impl
      - Counter Power
  - Day5
    - [RISC_V core on custom SOFA fabric](-risc_v-core-on-custom-sofa-fabric)
      - SOFA-RVMyth run
      - SOFA-RVMyth timing and area
      - RVMyth post impl netlist
      - SOFA-RVMyth Vivado simulation

------------------------------------------------------------------------------------------------------------------------------------
# Introduction to FPGA

After the complete design flow, ASICs are sent to the foundry for fabrication. Once fabrication is done, no change can be made on the IC, especially at the design level. This fact imposes a huge pressure on the reliabilty of the design. It'd be very useful (not just from monetary terms, but from time to market point of view as well)  to have a programmable device that could be used to test multiple design codes (reprogrammable). Research towards this goal yielded devices such as Programmable Logic Arrays (PLAs), Complex Programmable Logic Devices (CPLDs), and Field Programmable Gate Arrays (FPGAs). They basically synthesize a customizable hardware and this hardware could then be used to study the timing, power, and area parameters of the design. **This course uses Basys3 FPGA offered by Xilinx**

Just like we get the layout as the end product of the whole design procedure of an ASIC, we get a *BITSTREAM* in case of an FPGA. The architecture of an FPGA is explained using the below figure:

![image](https://user-images.githubusercontent.com/14873110/171280765-bd85f861-c70e-40fd-9e38-99fe0f7bae5a.png)



