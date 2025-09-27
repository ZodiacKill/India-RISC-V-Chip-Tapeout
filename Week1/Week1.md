🗺️ The RTL-GLS Flow: A Visual Guide
The entire process can be broken down into a series of logical steps, starting from your Verilog code and ending with a verified gate-level netlist.

1. RTL Design: You write your behavioral or RTL (Register Transfer Level) Verilog code, which describes your circuit's function.

2. Synthesis with Yosys: The Verilog code is fed into Yosys, an open-source synthesis tool. Yosys translates the RTL into a generic netlist, then optimizes it and maps it to a specific standard cell library (in this case, the Sky130 library).

3. GLS Netlist Generation: The final output of the synthesis process is a gate-level netlist, which is a structural description of your circuit using the standard cells from the library.

4. Gate-Level Simulation (GLS): The generated netlist is then simulated using a tool like Icarus Verilog. This simulation includes both the netlist and the standard cell models, allowing you to verify that the final hardware will behave exactly as your original RTL code intended.

<img width="696" height="561" alt="image" src="https://github.com/user-attachments/assets/d1596fb1-a5eb-4f38-9745-ea9b41456795" />




🗺️The main takeaways were:

  1. Synthesis Optimization: The opt_clean -purge command acts as a garbage collector, removing unused wires and logic to create a smaller, more efficient netlist.

  2. Intelligent Synthesis: Yosys intelligently handles designs with constant inputs and reset logic. It optimizes simple cases while preserving complex, functional behavior.

  3. Scalable Code: You used for-generate loops to create scalable designs like a MUX, a DEMUX, and a Ripple Carry Adder, avoiding repetitive code.

  4. Gate-Level Simulation (GLS): You learned that GLS is a critical step to verify that the synthesized netlist works exactly like your original RTL code, preventing a mismatch.

  5. Common Pitfalls: You were introduced to common design issues like latch inference from incomplete if/case statements and the risks of using blocking assignments in sequential logic.

  6. Our Design check and verification can be performed by same Testbench, because inputs and outputs along with the logic is same, just optimised as specified in .lib.

<p align="center">
<img src="https://img.shields.io/badge/Week%201-Completed-brightgreen?style=for-the-badge&logo=linux" alt="Week 1 Completed Badge"/>
<img src="https://img.shields.io/badge/RTL_Synthesis-Done-blue?style=for-the-badge&logo=github" alt="RTL Synthesis Badge"/>
<img src="https://img.shields.io/badge/GLS_Verification-Passed-success?style=for-the-badge&logo=git" alt="GLS Verification Badge"/>
<img src="https://img.shields.io/badge/Netlist%20-Simulated-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Netlist Simulated"/>
</p>



<p align="center">
<img src="https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Made in India"/>
</p>
