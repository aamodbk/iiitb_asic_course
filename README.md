# ASIC COURSE UPDATES
## Day 0
### Installation of required tools
The required tools IcarusVerilog, GTKWave tools can be installed with the following command.
```
sudo apt-get install iverilog gtkwave yosys
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/img1.png)
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/img2.png)
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/img3.png)
#### About Yosys
Yosys is an open-source framework for Verilog synthesis. It currently has extensive Verilog-2005 support and provides a basic set of synthesis algorithms for various application domains. Yosys can be adapted to perform any synthesis job by combining the existing passes (algorithms) using synthesis scripts and adding additional passes as needed by extending the Yosys C++ code base.

To install YoSys Synthesis tool, type the following in your terminal.
```
git clone https://github.com/YosysHQ/yosys.git
cd yosys 
sudo apt install make (If make is not installed please install it) 
sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
make config-gcc
make 
sudo make install
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/img4.png)
