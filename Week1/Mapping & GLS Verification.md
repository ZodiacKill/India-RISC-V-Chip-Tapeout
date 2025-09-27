<p align="center">
  <img src="https://img.icons8.com/color/452/india.png" width="60"/>
  <br/>
</p>

Objective: To observe how Yosys handles flip-flops with constant inputs and to verify the behavior using Gate-Level Simulation (GLS) with Icarus Verilog.

Process: Designs with constant-driven DFFs (const4.v and const5.v) were synthesized. The resulting netlists were then simulated alongside their original RTL using Icarus Verilog, including the Sky130 standard cell models.

Result: Yosys intelligently simplified constant-driven paths (using a buffer for a constant '1') while correctly preserving the functionality of DFFs with active reset logic. The GLS output matched the RTL simulation, confirming the functional correctness of the synthesized design.

Key Takeaway: Yosys performs smart optimization on constant values without compromising essential behavioral logic, such as reset. GLS is a vital step to validate this correctness.



 <p align="center">
  <img src="https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Made in India"/>
</p>
