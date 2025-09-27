<p align="center">
  <img src="https://img.icons8.com/color/452/india.png" width="60"/>
  <br/>
</p>

Objective: To understand how Yosys's opt_clean -purge command efficiently removes redundant logic from a synthesized netlist.

Process: Yosys was used to synthesize Verilog designs (opt_check4.v and multiple_module_opt.v). The opt_clean -purge command was executed after the initial synthesis and before technology mapping.

Result: The final netlists were significantly cleaner, with unnecessary wires and floating signals eliminated. This leads to a smaller, more efficient, and easier-to-debug circuit.

Key Takeaway: opt_clean -purge acts as a crucial "garbage collector" for your netlist, ensuring only essential circuitry remains.



 <p align="center">
  <img src="https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Made in India"/>
</p>
