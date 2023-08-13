# ASIC COURSE UPDATES
## Day 0
### Installation of required tools
#### About IcarusVerilog
Icarus Verilog is an open-source hardware description language (HDL) compiler and simulator. It is commonly used in digital design and verification to model and simulate hardware circuits written in the Verilog HDL. Iverilog can be utilized for various purposes, including digital system design, FPGA programming, ASIC development, and hardware verification.
One of the key advantages of Icarus Verilog is its open-source nature, enabling users to access and modify the source code to suit their specific needs. Additionally, it is widely used within the digital design community due to its efficiency and robustness, making it a popular choice for both beginners and experienced engineers in the field of digital hardware design.

#### About GTKWave
GTKWave is an open-source waveform viewer for digital signals and simulation results. It is commonly used in digital design and hardware verification to visualize and analyze waveforms generated by simulation tools like Icarus Verilog, ModelSim, and other HDL simulators.

The required tools IcarusVerilog, GTKWave tools can be installed with the following command.
```
sudo apt-get install iverilog gtkwave
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
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/yosys.png)

### About NGSpice
Ngspice is an open-source electronic circuit simulator that allows to analyze and simulate analog, digital, and mixed-signal circuits. Its code is based on three open source software packages: Spice3f5, Cider1b1 and Xspice. It is the open source successor of these venerable packages. It provides a powerful command-line interface for running simulations and can be used to model and test complex electronic designs, helping users understand circuit behavior, optimize performance, and ensure design reliability. With its wide range of supported circuit elements and models, Ngspice is a valuable tool in electronics design and education, aiding in the development and testing of electronic systems.

To install NGSpice follow the below steps.

First go to the following Sourceforge link -- [NGSpice - SourceForge](https://sourceforge.net/projects/ngspice/) and unzip the package into your device.
Next type the below commands into your terminal while in the `ngspice-40` directory.
```
sudo apt-get install libxaw7-dev build-essential
sudo ./compile_linux.sh
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/ngspice.png)

### About OPENSTA
OpenSTA is an open-source static timing analysis tool used in digital integrated circuit design. It helps engineers analyze the timing of digital circuits to ensure that signals propagate correctly and meet required timing constraints. By considering factors such as signal delays and logic paths, OpenSTA assists in identifying potential timing violations and aids in optimizing circuit performance. It plays a crucial role in verifying the timing correctness of complex digital designs before fabrication, contributing to the overall reliability and functionality of integrated circuits.

To install OpenSTA, type the following into your terminal.
```
sudo apt-get install cmake clang gcc tcl swig bison flex
git clone https://github.com/The-OpenROAD-Project/OpenSTA.git
cd OpenSTA
mkdir build
cd build
cmake ..
make
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/opensta.png)

### About Magic
Magic is an electronic design automation (EDA) layout tool for very-large-scale integration (VLSI) integrated circuit (IC) originally written by John Ousterhout and his graduate students at UC Berkeley. Due largely in part to its liberal Berkeley open-source license, magic has remained popular with universities and small companies. The open-source license has allowed VLSI engineers with a bent toward programming to implement clever ideas and help magic stay abreast of fabrication technology. However, it is the well thought-out core algorithms which lend to magic the greatest part of its popularity. Magic is widely cited as being the easiest tool to use for circuit layout, even for people who ultimately rely on commercial tools for their product design flow.

For installation of magic, type the following commands in your terminal to install dependencies:
```
sudo apt-get install m4
sudo apt-get install csh
sudo apt-get install tcsh
sudo apt-get install libx11-dev
sudo apt-get install tcl-dev tk-dev
sudo apt-get install libcairo2-dev
sudo apt-get install mesa-common-dev libglu1-mesa-dev
sudo apt-get install libncurses-dev
```

To install Magic, type the following in the terminal:
```
$   git clone https://github.com/RTimothyEdwards/magic
$   cd magic
$   ./configure
$   sudo make
$   sudo make install
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/magic.png)

### About OpenLane
OpenLane is an open-source VLSI flow built around open-source tools. That is, it's a collection of scripts that run these tools, in the right order, transforming their inputs and outputs as appropriate, and organising the results. It is an automated RTL to GDSII flow based on several components including OpenROAD, Yosys, Magic, Netgen, CVC, SPEF-Extractor, CU-GR, Klayout and a number of custom scripts for design exploration and optimization. The flow performs full ASIC implementation steps from RTL all the way down to GDSII.
For installation of OpenLane, type the follow the below steps.

Installing python as it is a pre-requisite:
```
$   sudo apt install -y build-essential python3 python3-venv python3-pip
```
For installing Docker Engine on Ubuntu, use the following link -- https://docs.docker.com/engine/install/ubuntu/.

Next, go to your main directory and type the following in the terminal:

```
$   git clone https://github.com/The-OpenROAD-Project/OpenLane.git
$   cd OpenLane
$   sudo make
```

Now, to check that OpenLane dependencies are succesfully installed, run the test command:

```
$   sudo make test
```
If the line `Basic test passed` is printed in the terminal, then the installation is successful.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/openlane.png)

## Day 1
### Verilog RTL Design
Verilog RTL (Register Transfer Level) design is a methodology for describing digital circuits at a higher abstraction level, focusing on how data flows and is manipulated within registers and logic elements. It's a key step in digital design before actual implementation. Icarus Verilog is an open-source Verilog compiler and simulator that helps translate RTL descriptions into simulations. It compiles Verilog code and simulates its behavior, enabling designers to test and verify their digital circuits' functionality.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/iverilog_gtkwave.png)

Once Verilog RTL code is written and simulated using Icarus Verilog, designers can use GTKWave, an open-source waveform viewer, to visualize the simulation results. GTKWave allows users to load and inspect waveforms generated during the simulation, helping them understand signal interactions, timing relationships, and overall circuit behavior. This combined workflow of Verilog RTL design, synthesis using Icarus Verilog, and waveform analysis using GTKWave is crucial for designing, testing, and validating digital circuits before moving on to the synthesis of the RTL design into gate level using the Yosys tool.

Given below are the steps to follow to perform an initial RTL design and synthesis as explained above.
Type the below commands into the terminal while in your main directory to install the required verilog design files.
```
git clone https://github.com/kunalg123/vsdflow.git
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```
The directory `sky130RTLDesignAndSynthesisWorkshop/verilog_files/` contains a number of verilog designa dn testbench files for simulation. Below steps show the simulation of one of those examples.
Enter the directory mentioned above and type the following commands.
```
iverilog good_mux.v tb_good_mux.v
./a.out
gtkwave tb_good_mux.vcd
```
The first two lines compile and execute the design and testbench files for the example good MUX and the last line opens GTKWave to visualize the results of the testbench simulation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/sim_result.png)

### Synthesis of RTL Design into Gate level netlist
After designing and simulating a digital circuit using Verilog RTL and tools like Icarus Verilog and GTKWave, the next step is synthesis into a gate-level netlist using Yosys. This gate-level netlist serves as an intermediary step between the RTL description and the actual hardware implementation. Yosys optimizes the design, mapping it to specific target technology libraries or FPGA architectures, and generates an optimized netlist that can be further analyzed and prepared for physical layout and fabrication.

## Contributors
* Aamod B K
* Kunal Ghosh

## Acknowledgments
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.

## Contact Information
* Aamod B K, IMtech 2020, International Institute of Information Technology, Bangalore Aamod.BK@iiitb.ac.in
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. kunalghosh@gmail.com

## References
* Wikipedia -- https://en.wikipedia.org/wiki/Logic_synthesis
* IcarusVerilog Wikipedia -- https://en.wikipedia.org/wiki/Icarus_Verilog
* Yosys Documentation -- https://yosyshq.net/yosys/
* Magic -- http://www.opencircuitdesign.com/magic/; https://en.wikipedia.org/wiki/Magic_(software)#:~:text=Magic%20is%20an%20electronic%20design,the%20project%20in%20February%201983.
* OpenLane -- https://github.com/The-OpenROAD-Project/OpenLane
* NGspice -- https://ngspice.sourceforge.io/presentation.html
* OpenSTA -- https://github.com/The-OpenROAD-Project/OpenSTA
