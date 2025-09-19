📅 Week 0 — Environment Setup & Tool Installation
This initial phase focused on preparing the complete software environment required for the SoC design journey.

Task	Description	Status
Task 0	📂 Repository Setup — Initialized this GitHub repository to serve as the official project log.	✅ Done
Task 1	🛠️ EDA Toolchain Installation — Installed the full suite of open-source tools for the RTL-to-GDSII flow, including Iverilog, GTKWave, Yosys, Magic, ngspice, and OpenLane.	✅ Done

Export to Sheets
🌟 Key Learnings from Week 0
Successfully installed and verified a complete open-source EDA toolchain on an Ubuntu VM.

Learned the intricacies of environment setup and dependency management for complex VLSI projects.

Established a robust system ready for the upcoming RTL → GDSII flow experiments.

⚙️ Detailed Installation Commands
<details>
<summary>Click to view the step-by-step installation commands for each tool.</summary>

Icarus Verilog (iverilog) & GTKWave
Bash

sudo apt-get update
sudo apt-get install iverilog
sudo apt-get install gtkwave
Yosys (Synthesis Tool)
Bash

git clone https://github.com/YosysHQ/yosys.git
cd yosys
sudo apt-get install build-essential clang bison flex libreadline-dev gawk tcl-dev libffi-dev git graphviz xdot pkg-config python3 libboost-system-dev libboost-python-dev libboost-filesystem-dev zlib1g-dev
make config-gcc
make
sudo make install
Magic (VLSI Layout Tool)
Bash

sudo apt-get install m4 tcsh csh libx11-dev tcl-dev tk-dev libcairo2-dev mesa-common-dev libglu1-mesa-dev libncurses-dev
git clone https://github.com/RTimothyEdwards/magic.git
cd magic
./configure
make
sudo make install
ngspice (Circuit Simulator)
Bash

# Download tarball, then:
tar -zxvf ngspice-37.tar.gz
cd ngspice-37/release
../configure --with-x --with-readline=yes --disable-debug
make
sudo make install
OpenLane (Automated RTL to GDSII Flow)
Bash

# Install Docker first, then add user to docker group and reboot
# For full Docker commands, refer to the official documentation.
sudo usermod -aG docker $USER
# --- REBOOT ---
cd $HOME
git clone https://github.com/The-OpenROAD-Project/OpenLane.git
cd OpenLane
make
make test
</details> 
