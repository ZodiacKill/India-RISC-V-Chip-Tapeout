<p align="center">
  <img src="https://img.icons8.com/color/452/india.png" width="60"/>
  <br/>
</p>
Mapping (RTL → Standard Cells)

## 🔎 Why Mapping?  
- After optimization, the circuit is still in **abstract logic form** (AND, OR, DFF, etc).  
- Mapping converts this into **real Sky130 standard cell instances** (like `sky130_fd_sc_hd__and2_0`, `sky130_fd_sc_hd__dfxtp_1`, etc).  
- Ensures the design is **ready for fabrication**.  

Objective: To observe how Yosys handles flip-flops with constant inputs and to verify the behavior using Gate-Level Simulation (GLS) with Icarus Verilog.

Process: Designs with constant-driven DFFs (const4.v and const5.v) were synthesized. The resulting netlists were then simulated alongside their original RTL using Icarus Verilog, including the Sky130 standard cell models.

## 🛠️ Key Commands  

 Map flip-flops to library cells
 
         dfflibmap -liberty sky130_fd_sc_hd__tt_025C_1v80.lib  

 Map combinational logic (AND, OR, MUX) to library cells
 
    abc -liberty sky130_fd_sc_hd__tt_025C_1v80.lib
Explanation:

dfflibmap → specifically targets sequential elements (registers/FFs).

abc → optimizes and maps combinational logic to available standard cells.



## 📊 Result:
Yosys intelligently simplified constant-driven paths (using a buffer for a constant '1') while correctly preserving the functionality of DFFs with active reset logic. The GLS output matched the RTL simulation, confirming the functional correctness of the synthesized design.

Design	RTL Behavior	Mapped Result

const4.v	Flops always latched 1	Replaced with buffers only

const5.v	Flops with reset logic	Flops preserved with reset functionality

👉 Observation:

Yosys is smart in mapping:

If a register holds a constant → replaces with buffer/gate.

If reset/clock logic is critical → keeps the FF intact.

📝 Mini Example
      RTL (const4.v):
      
      verilog
      module const4 (input clk, output reg q);
        always @(posedge clk) begin
          q <= 1'b1;
        end
      endmodule
Mapped Netlist (after Yosys):

      verilog
      
      module const4 (input clk, output q);
        sky130_fd_sc_hd__buf_1 u1 (.A(1'b1), .X(q));
      endmodule
✅ FF replaced with a buffer since output is always 1.

🔗 Analogy
Mapping is like using real Lego blocks 🧱 instead of abstract shapes.

Before: you know you need “a flip-flop” or “an AND gate”.

After: you physically choose from Sky130’s catalog of cells to build the actual circuit.


## ✅Key Takeaway: 
Yosys performs smart optimization on constant values without compromising essential behavioral logic, such as reset. GLS is a vital step to validate this correctness.



 <p align="center">
  <img src="https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Made in India"/>
</p>
