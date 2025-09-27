<p align="center">
  <img src="https://img.icons8.com/color/452/india.png" width="60"/>
  <br/>
</p>

Objective: To confirm that Yosys correctly synthesizes complex, scalable designs created using for-generate loops and that their gate-level netlists are functionally equivalent to the original RTL.

Process: A MUX, a DEMUX, and a Ripple Carry Adder (RCA), all built using for-generate or generate statements, were synthesized. Each final netlist was then simulated against its original RTL using GLS.

Result: For all three designs, the GLS simulation waveforms perfectly matched the RTL waveforms.

Key Takeaway: The use of for-generate and generate allows for clean, modular, and scalable Verilog code. GLS is essential for verifying that the synthesis tool correctly translates these high-level constructs into the desired hardware.

 <p align="center">
  <img src="https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Made in India"/>
</p>
