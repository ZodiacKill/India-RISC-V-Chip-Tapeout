<p align="center">
  <img src="https://img.icons8.com/color/452/india.png" width="60"/>
  <br/>
</p>

## 🔎 Why GLS?  
- RTL simulation = checks your **intent**.  
- GLS = checks your **actual netlist** after synthesis + mapping.  
- Ensures **no mismatch** between RTL and synthesized hardware.  

👉 Think of GLS as the **reality check** 🕵️.  

---
Objective: To confirm that Yosys correctly synthesizes complex, scalable designs created using for-generate loops and that their gate-level netlists are functionally equivalent to the original RTL.

Process: A MUX, a DEMUX, and a Ripple Carry Adder (RCA), all built using for-generate or generate statements, were synthesized. Each final netlist was then simulated against its original RTL using GLS.

## 🛠️ GLS Flow  

1. Compile with primitives + Sky130 cell models

        iverilog ../my_lib/verilog_models/primitives.v \
                ../my_lib/verilog_models/sky130_fd_sc_hd.v \
                design_GLS.v tb_design.v

2. Run simulation
   
        ./a.out

4. View waveform
   
        gtkwave dump.vcd

## Result:
<table>
  <tr>
    <th>Design</th>
    <th>RTL Behavior</th>
    <th>GLS (Gate-Level) Result</th>
  </tr>
  <tr>
    <td>mux_generate.v</td>
    <td>MUX outputs matched expected behavior</td>
    <td>✅ GLS waveforms identical to RTL</td>
  </tr>
  <tr>
    <td>demux_generate.v</td>
    <td>DEMUX routed inputs correctly</td>
    <td>✅ GLS confirmed correct routing</td>
  </tr>
  <tr>
    <td>rca.v (Ripple Adder)</td>
    <td>Addition + carry chain works</td>
    <td>✅ GLS matched RTL addition results</td>
  </tr>
  <tr>
    <td>const4.v / const5.v</td>
    <td>Constants & reset behavior checked</td>
    <td>✅ GLS confirmed simplification + resets</td>
  </tr>
</table>
For all three designs, the GLS simulation waveforms perfectly matched the RTL waveforms.


⚠️ Common Pitfalls Found in GLS

Blocking (=) vs Non-Blocking (<=)

    Blocking inside sequential always block → simulation vs synthesis mismatch.
    
    ✅ Rule: Use <= for clocked always blocks.

Latch Inference

    Missing else or default → unintended latch created.
    
    ✅ Always cover all conditions.

Sim–Synth Mismatch

    Example: combinational assignments using old values.
    
    ✅ GLS exposes these mismatches early.
    
#📝 Mini Example

    RTL (mux.v):
    
    module mux(input a, b, sel, output y);
      assign y = sel ? b : a;
    endmodule


Simulation Results:

RTL sim → Correct muxing.

GLS sim → Matches perfectly after mapping to Sky130 cells.

🧠 Key Takeaways

1. GLS = golden verification step.

2. Validates that synthesis + mapping did not break logic.

3. Essential for complex designs (MUX, DEMUX, RCA, etc).

4. Prevents nasty surprises before physical design.

👉 If RTL is your plan, GLS is the reality check ✅.

The use of for-generate and generate allows for clean, modular, and scalable Verilog code. GLS is essential for verifying that the synthesis tool correctly translates these high-level constructs into the desired hardware.

 <p align="center">
  <img src="https://img.shields.io/badge/Made%20in-India-FF9933?style=for-the-badge&logo=india&logoColor=white" alt="Made in India"/>
</p>
