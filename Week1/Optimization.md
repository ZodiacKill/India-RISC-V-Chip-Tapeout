<p align="center">
  <img src="https://img.icons8.com/color/452/india.png" width="60"/>
  <br/>
</p>

Objective: To understand how Yosys's opt_clean -purge command efficiently removes redundant logic from a synthesized netlist.

Process: Yosys was used to synthesize Verilog designs (opt_check4.v and multiple_module_opt.v). The opt_clean -purge command was executed after the initial synthesis and before technology mapping.

Result: The final netlists were significantly cleaner, with unnecessary wires and floating signals eliminated. This leads to a smaller, more efficient, and easier-to-debug circuit.

Key Takeaway: opt_clean -purge acts as a crucial "garbage collector" for your netlist, ensuring only essential circuitry remains.

<table>
  <tr>
    <th>Aspect</th>
    <th>Before Optimization</th>
    <th>After Optimization</th>
  </tr>
  <tr>
    <td>Wires & Signals</td>
    <td>Extra wires, floating nets</td>
    <td>✅ Removed, only necessary remain</td>
  </tr>
  <tr>
    <td>Gates & Cells</td>
    <td>Redundant logic kept</td>
    <td>✅ Clean, minimal set of gates</td>
  </tr>
  <tr>
    <td>Readability</td>
    <td>Messy, harder to debug</td>
    <td>✅ Compact, easy to trace</td>
  </tr>
  <tr>
    <td>Area & Power</td>
    <td>Higher consumption</td>
    <td>✅ Reduced usage</td>
  </tr>
</table>

 <p align="center">
  <img src="https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Made in India"/>
</p>
