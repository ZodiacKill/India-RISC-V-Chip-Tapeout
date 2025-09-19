Week 0 — Environment Setup & Tool Installation

This week focused on building the complete development environment required for the SoC design journey. From VM setup to installing a full open-source EDA toolchain, the system is now ready for RTL → GDSII flow .

System Requirements
| Component           | Specification ✅   |
| ------------------- | ----------------- |
| **OS**              | Ubuntu 20.04+     |
| **CPU**             | 4 vCPUs           |
| **RAM**             | 6 GB+             |
| **Storage**         | 50 GB+ HDD        |


| Task                  | Description                                                     | Status |
| --------------------- | --------------------------------------------------------------- | ------ |
| 📂 **Repo & Docs**    | Created GitHub repo + documented intro video summary            | ✔️ Done |
| 🛠️ **EDA Toolchain** | Installed + verified complete open-source flow (with snapshots) | ✔️ Done |

Key Learnings

Gained hands-on experience in environment setup & dependency management for VLSI projects.

Successfully installed and verified open-source EDA toolchain on Ubuntu VM.

Established a robust base system to smoothly proceed with RTL → GDSII flow.

⚙️ Installed EDA Tools
| Tool                         | Purpose                                    | Verification |
| ---------------------------- | ------------------------------------------ | ------------ |
| **Icarus Verilog + GTKWave** | Verilog simulation & waveform analysis     | ✔️            |
| **Yosys**                    | RTL Synthesis                              | ✔️            |


Installation Highlights
<details> <summary><b>Step-by-Step Setup (Click to Expand)</b></summary>

1️ Yosys → Built from source for RTL synthesis.

commands-
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

<img width="1073" height="241" alt="image" src="https://github.com/user-attachments/assets/d3f767eb-c6ec-4cf1-bf81-a74009cebb3b" />

2️ Icarus Verilog & GTKWave → Installed via APT for simulation & waveform viewing.

commands-
Steps to install iverilog
sudo apt-get update
sudo apt-get install iverilog
<img width="996" height="771" alt="image" src="https://github.com/user-attachments/assets/7f33dda1-6c15-47b6-bbc8-e4e33786e31d" />

Steps to install gtkwave
sudo apt-get update
sudo apt install gtkwave 
<img width="1070" height="157" alt="image" src="https://github.com/user-attachments/assets/7cfcbc1d-7898-47de-a7ca-533c3e767eb2" />



</details>
 Week 0 Milestone

✔️ Environment fully ready for SoC design flow
✔️ GitHub repo + documentation prepared
✔️ All tools tested & verified

 Next Week (Week 1): RTL Design & Simulation Kickoff ⚡
