Week 0   Environment Setup & Tool Installation

This week focused on building the complete development environment required for the SoC design journey. From VM setup to installing a full open-source EDA toolchain, the system is now ready for RTL → GDSII flow.

 Tasks Completed
<table> <tr> <th>Task</th> <th>Description</th> <th>Status</th> </tr> <tr> <td>📂 Repo & Docs</td> <td>Created GitHub repo + documented intro video summary</td> <td><img src="https://img.shields.io/badge/Done-✔️-brightgreen?style=flat-square"/></td> </tr> <tr> <td>🛠️ EDA Toolchain</td> <td>Installed + verified complete open-source flow (with snapshots)</td> <td><img src="https://img.shields.io/badge/Done-✔️-brightgreen?style=flat-square"/></td> </tr> </table>
 Key Learnings

 Hands-on experience with environment setup & dependency management for VLSI projects.

 Successfully installed & verified open-source EDA toolchain on Ubuntu VM.

 Built a robust base system to smoothly proceed with RTL → GDSII flow.

⚙️ Installed EDA Tools

<table> <tr> <th>Tool</th> <th>Purpose</th> <th>Status</th> </tr> <tr> <td>⚡ Icarus Verilog + GTKWave</td> <td>Verilog simulation & waveform analysis</td> <td>✔️ Verified</td> </tr> <tr> <td>🔧 Yosys</td> <td>RTL Synthesis</td> <td>✔️ Verified</td> </tr> </table>
 Installation Highlights
 <summary><b>Step-by-Step Setup (Click to Expand)</b></summary>

Yosys
 Built Yosys from source
 
 $ sudo apt-get update
 
$ git clone https://github.com/YosysHQ/yosys.git

$ cd yosys

$ sudo apt install make (If make is not installed please install it)

$ sudo apt-get install build-essential clang bison flex \
 libreadline-dev gawk tcl-dev libffi-dev git \
 graphviz xdot pkg-config python3 libboost-system-dev \
 libboost-python-dev libboost-filesystem-dev zlib1g-dev
 
$ make config-gcc

$ make

$ sudo make install

<img width="1073" height="241" alt="Screenshot From 2025-09-19 15-48-30" src="https://github.com/user-attachments/assets/168d0af8-6e99-4e4f-8465-b70e63c94b6a" />


 Installed Icarus Verilog & GTKWave via APT
 Steps to install iverilog
 
sudo apt-get update

sudo apt-get install iverilog

<img width="996" height="771" alt="Screenshot From 2025-09-19 15-52-04" src="https://github.com/user-attachments/assets/fb21fceb-8f75-44e4-b0a3-cbe7bc84c050" />
Steps to install gtkwave

sudo apt-get update

sudo apt install gtkwave 

<img width="1070" height="157" alt="Screenshot From 2025-09-19 15-55-44" src="https://github.com/user-attachments/assets/dda0459c-a7d2-4247-94a9-df4f4dd856b4" />



 Week 0 Milestone

✔️ Environment fully ready for SoC design flow
✔️ GitHub repo + documentation prepared
✔️ All EDA tools tested & verified

<p align="center"> <img src="https://img.shields.io/badge/Week%200-Completed-brightgreen?style=for-the-badge&logo=github"/> <img src="https://img.shields.io/badge/Next%20Step-RTL%20Design%20⚡-blue?style=for-the-badge"/> </p>

🔜 Next Week (Week 1): RTL Design & Simulation Kickoff ⚡
