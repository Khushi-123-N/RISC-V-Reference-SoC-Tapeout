# Week0 README and Assets Structure

# Week 0 – RISC-V Reference SoC Tapeout Program

This folder contains the assets, diagrams, and tool installation references for Week 0 of the RISC-V Reference SoC Tapeout Program.

## Task-1: GitHub Repository

* A GitHub repository has been created to document the **summary of the previous video**.
* Reference for structure: [SFAL VSD Reference Repo](https://github.com/sukanyasmeher/sfal-vsd?tab=readme-ov-file#day-0---tools-installation)

## Contents of Week0

```
Week0/
├── README.md
└── assets/
    ├── diagrams/
    │    └── vsd_flow.png
    ├── gtkwave_installed.png
    ├── iverilog_installed.png
    ├── magic_vlsi_installed.png
    ├── ngspice_installed.png
    └── yosys_installed.png
```

* `assets/diagrams/` → Main flow diagram for VSD
* Tool installation snapshots (existing images):

  * `gtkwave_installed.png` → GTKWave installed
  * `iverilog_installed.png` → Icarus Verilog installed
  * `magic_vlsi_installed.png` → Magic VLSI installed
  * `ngspice_installed.png` → NGSpice installed
  * `yosys_installed.png` → Yosys installed

> **Note:** These images show confirmation that the respective tools were installed successfully.

## Task-2: Tool Installation Summary

**System Configuration Required:**

* Ubuntu 20.04+
* 6 GB RAM, 50 GB HDD
* 4 vCPU

**Tool Installation Steps (Summary):**

### 1. Yosys

```bash
sudo apt-get update
git clone https://github.com/YosysHQ/yosys.git
cd yosys
sudo apt install make build-essential clang bison flex libreadline-dev gawk tcl-dev libffi-dev git graphviz xdot pkg-config python3 libboost-system-dev libboost-python-dev libboost-filesystem-dev zlib1g-dev
make config-gcc
make
sudo make install
```

### 2. Icarus Verilog

```bash
sudo apt-get update
sudo apt-get install iverilog
```

### 3. GTKWave

```bash
sudo apt-get update
sudo apt install gtkwave
```

### 4. NGSpice

```bash
tar -zxvf ngspice-37.tar.gz
cd ngspice-37
mkdir release
cd release
../configure --with-x --with-readline=yes --disable-debug
make
sudo make install
```

### 5. Magic VLSI

```bash
sudo apt-get install m4 tcsh csh libx11-dev tcl-dev tk-dev libcairo2-dev mesa-common-dev libglu1-mesa-dev libncurses-dev
git clone https://github.com/RTimothyEdwards/magic
cd magic
./configure
make
sudo make install
```

### 6. OpenLane

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt install -y build-essential python3 python3-venv python3-pip make git
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
sudo docker run hello-world
sudo groupadd docker
sudo usermod -aG docker $USER
sudo reboot
cd $HOME
git clone https://github.com/The-OpenROAD-Project/OpenLane
cd OpenLane
make
make test
```

### Check Dependencies

```bash
git --version
docker --version
python3 --version
make --version
python3 -m venv -h
```
