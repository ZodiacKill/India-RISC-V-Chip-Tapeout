<p align="center">
  <img src="https://img.icons8.com/color/452/india.png" width="60"/>
  <br/>
</p>

Yosys 




This flow takes your Verilog code and converts it into a gate-level netlist, which is a structural description of your circuit using standard cells from the specified library. The process includes synthesis, optimization, and technology mapping to prepare the design for physical implementation.

<table>
  <tr>
    <td>Step</td>
    <td>Command</td>
    <td>Purpose</td>
  </tr>
  <tr>
    <td>1️⃣</td>
    <td>read_liberty -lib ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib</td>
    <td>Load standard-cell library</td>
  </tr>
  <tr>
    <td>2️⃣</td>
    <td>read_verilog const4.v</td>
    <td>Read RTL source</td>
  </tr>
  <tr>
    <td>3️⃣</td>
    <td>synth -top const4</td>
    <td>Run synthesis</td>
  </tr>
  <tr>
    <td>4️⃣</td>
    <td>dfflibmap -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib</td>
    <td>Map flip-flops to technology cells</td>
  </tr>
  <tr>
    <td>5️⃣</td>
    <td>abc -liberty ../my_lib/lib/sky130_fd_sc_hd__tt_025C_1v80.lib</td>
    <td>Optimize & tech-map logic</td>
  </tr>
  <tr>
    <td>6️⃣</td>
    <td>write_verilog const4_net.v</td>
    <td>Save synthesized netlist</td>
  </tr>
</table>


 <p align="center">
  <img src="https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Made in India"/>
</p>
