


<p align="center">
<img src="https://img.icons8.com/color/452/india.png" width="60"/>



</p>

Week 1: RTL-GLS
This week focused on the core RTL → Gate-Level Synthesis (GLS) flow.

We translated behavioral Verilog into a physical netlist and verified its functional correctness through simulation, confirming the design is ready for the next stages of the physical design journey.

📋 Tasks Completed
<table>
<tr>
<th>Task</th>
<th>Description</th>
<th>Status</th>
</tr>
<tr>
<td>🧹 Yosys Optimization</td>
<td>Explored opt_clean -purge to remove redundant logic and wires</td>
<td><img src="https://img.shields.io/badge/Done-✔️-brightgreen?style=flat-square"/></td>
</tr>
<tr>
<td>🔗 GLS Verification</td>
<td>Performed Gate-Level Simulation on constant DFFs and scalable designs (MUX, DEMUX, RCA)</td>
<td><img src="https://img.shields.io/badge/Done-✔️-brightgreen?style=flat-square"/></td>
</tr>
</table>




<img width="696" height="561" alt="image" src="https://github.com/user-attachments/assets/d1596fb1-a5eb-4f38-9745-ea9b41456795" />



🧠 Key Learnings
Optimization is Key: The opt_clean -purge command acts as a garbage collector for Yosys, removing unused nets and cells to produce a clean and efficient netlist.

Yosys is Smart: The tool intelligently handles constant propagation and reset logic in flip-flops, simplifying the circuit without losing critical functionality.

Scalable Design: for-generate loops are a powerful way to write clean, modular, and scalable Verilog code for repetitive structures like MUXes, DEMUXes, and adders.

Verify Everything: Gate-Level Simulation (GLS) is a crucial step to prove that the synthesized netlist behaves exactly as the original RTL design. This prevents a simulation-synthesis mismatch.

Single Testbench: We confirmed that the same testbench can be used for both RTL and GLS, as the inputs, outputs, and overall logic remain the same—only the internal implementation is optimized.

⚙️ Tools Used
<table>
<tr>
<th>Tool</th>
<th>Purpose</th>
<th>Status</th>
</tr>
<tr>
<td>⚡ Icarus Verilog + GTKWave</td>
<td>GLS verification & waveform analysis</td>
<td>✔️ Verified</td>
</tr>
<tr>
<td>🔧 Yosys</td>
<td>RTL Synthesis & Optimization</td>
<td>✔️ Verified</td>
</tr>
</table>

🗺️ The RTL-GLS Flow
The process involves a series of logical steps, starting from your Verilog code and ending with a verified gate-level netlist.

RTL Design: You write your behavioral or RTL (Register Transfer Level) Verilog code, which describes your circuit's function.

Synthesis with Yosys: The Verilog code is fed into Yosys, which translates the RTL into a generic netlist, then optimizes it and maps it to a specific standard cell library (in this case, the Sky130 library).

GLS Netlist Generation: The final output of the synthesis process is a gate-level netlist, a structural description of your circuit using the standard cells from the library.

Gate-Level Simulation (GLS): The generated netlist is then simulated using a tool like Icarus Verilog. This simulation verifies that the final hardware will behave exactly as your original RTL code intended.

Week 1 Milestone
✔️ RTL Design & Synthesis Done
✔️ Netlist Generated and Verified
✔️ GLS Simulation Confirmed Functional Correctness

<p align="center">
<img src="https://img.shields.io/badge/Week%201-Completed-brightgreen?style=for-the-badge&logo=linux"/>
<img src="https://img.shields.io/badge/RTL_Synthesis-Done-blue?style=for-the-badge&logo=github"/>
<img src="https://img.shields.io/badge/GLS_Verification-Passed-success?style=for-the-badge&logo=git"/>
<img src="https://img.shields.io/badge/Netlist%20-Simulated-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Netlist Simulated"/>
</p>

 Key Concepts & Learnings
Gate-Level Simulation (GLS): GLS is a critical verification step that ensures the synthesized gate-level netlist is functionally identical to the original RTL design. It validates the structural integrity of the synthesized circuit.

Latency & Blocking Assignments: Be careful with blocking (=) and non-blocking (<=) assignments. A mismatch between simulation and synthesis can occur when using blocking assignments for sequential logic, potentially leading to incorrect hardware.

Latch Inference: Incomplete if or case statements can cause a synthesis tool to infer an unintended latch. This is a common design flaw that should be avoided by using a default case or ensuring all conditions are covered.

<p align="center">
<img src="https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Made in India"/>
</p>
