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

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/yosys_synth.png)

After following the steps to synthesis and obtaining the netlist, we can verify our netlist by perfoming Gate Level Simulation (GLS). Netlist is translation from RTL into Gates and connection wirings with full functional and timing behaviour. To obtain netlist using synthesis, we need a library of all available standard cells in the form of `.lib` files. The inclusion of these files along with the netlist synthesis is done using the following steps.
Type the given commands into the terminal while in the directory `sky130RTLDesignAndSynthesisWorkshop/verilog_files/`.
```
yosys
yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> read_verilog good_mux.v
yosys> abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> show
yosys> write_verilog -noattr good_mux_netlist.v
```
The `read_verilog` command displays the statistics of the netlist and the `show` command displays the netlist in a `.dot` file format.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/stat_synth.png)

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_synth.png)

The `write_verilog` command writes the current design into a netlist file. We can then perform verification of GLS by running the following command.

```
iverilog -DFUNCTIONAL -DUNIT_DELAY=#1 ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v good_mux_netlist.v tb_good_mux.v
./a.out
gtkwave tb_good_mux.vcd
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/gls.png)

## Day 2
### Contents of the library (.lib) file
The below image shows the top contents of the file `sky130_fd_sc_hd__tt_025C_1v80.lib`.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/lib.png)

The beginning of the code mainly shows the standard parameters for the synthesis like the technlogy used (CMOS in this case), the delay model, units of various physical quantities etc.
Also as explained above it contains a variety of different standard cells along with their features.
Taking an example of a 2-input AND into the first input of a 4-input NOR gate (`!( ( A1 & A2 ) | B1 | C1 | D1 )`),
we see that there are several versions of the same standard cell.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/ver.png)

### Hierarchical Synthesis and Flat Synthesis
Hierarchical synthesis involves synthesizing a complex design by breaking it down into various sub-modules, where each module is synthesized separately to generate gate-level netlists and then integrated. Hierarchical synthesis allows for better organization, reuse of modules, and incremental changes to the design without affecting the entire system.
Flat synthesis, on the other hand, treats the entire design as a single, monolithic unit during the synthesis process and regardless of any hierarchical relations, it is synthesized into a single netlist. Flat synthesis can be useful for optimizing certaijn designs but it becomes challenging to maintain, analyze, and modify the design due to its lack of structural modularity.

We see an example of hierarchical and flat synthesis in the `multiple_modules.v` file in the `sky130RTLDesignAndSynthesisWorkshop/verilog_files/` directory.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/mm.png)

To perform hierarchical synthesis on the `multiple_modules.v` file type the following commands.
```
yosys
yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> read_verilog multiple_modules.v
yosys> synth -top multiple_modules
yosys> abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> show multiple_modules
yosys> write_verilog multiple_modules_hier.v
```
The following statistics are displayed.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/stat_mm_h.png)

The following netlist is displayed.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_mm_h.png)

To perform flat synthesis on the `multiple_modules.v` file type the following commands.
```
yosys
yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> read_verilog multiple_modules.v
yosys> synth -top multiple_modules
yosys> abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> flatten
yosys> show
yosys> write_verilog multiple_modules_flat.v
```

The following netlist is displayed.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_mm_f.png)

To synthesise each sub-module separately type in the following commands.
```
yosys
yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> read_verilog multiple_modules.v
yosys> synth -top sub_module1
yosys> abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> show
yosys> write_verilog multiple_modules_flat.v
```
The following statistics are displayed.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/stat_mm_sub.png)

The following netlist is displayed.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_mm_sub.png)

### Flip-Flop Coding Styles and Optimizations
Flip-Flops are an essential part of sequential logic in a circuit and here we explore the design and synthesis of various types of flip-flops.
The steps to compile, view waveform and also synthesise the different types of flip-flops are given below.

**Asynchronous-Reset FF**
```
iverilog dff_asyncres.v tb_dff_asyncres.v
./a.out
gtkwave tb_dff_asyncres.vcd
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/asyncres.png)
```
yosys
yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> read_verilog dff_asyncres.v
yosys> synth -top dff_asyncres
yosys> dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> show
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_asyncres.png)

**Synchronous-Reset FF**
```
iverilog dff_syncres.v tb_dff_syncres.v
./a.out
gtkwave tb_dff_syncres.vcd
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/syncres.png)
```
yosys
yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> read_verilog dff_syncres.v
yosys> synth -top dff_syncres
yosys> dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> show
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_syncres.png)

**Asynchronous-Set FF**
```
iverilog dff_async_set.v tb_dff_async_set.v
./a.out
gtkwave tb_dff_async_set.vcd
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/async_set.png)
```
yosys
yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> read_verilog dff_async_set.v
yosys> synth -top dff_async_set
yosys> dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
yosys> show
```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_async_set.png)

**Optimisations**
Taking the example of multiplication of a binary number by 2, `mult_2.v`, since it requires on left-shifting of the bits and appending the LSB bits with 0s, it does not require the use of any standard cells and is thus very optimal.
The netlist obtained for this code is:
```

```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/mult_2.png)

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_mult_2.png)

Similarly as a multiplication by 8 requires left-shifting the bits by 3 bits, the netlist obtained for the code is:
```

```
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/mult_8.png)

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_mult_8.png)

## Day 3
### Combinational Optimisations
**Contant Propagation**
Due to the fixed nature of some inputs, transistor logic can sometimes be optimised to use a much lower number of transistors than actually required.
Eg:
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/con_prop.png)

**Boolean Logic Optimisation**
The boolean expression of combinatorial logic can also sometimes be simplified into much smaller forms as seen in the example below:
Eg: The logic `assign y = a?(b?c:(c?a:0)):(!c);` can be simplified into the logic `assign y = a ^ c`.

**Examples**
Reducible boolean logic in the netlist can be optimised during synthesis using the `opt_clean` command in yosys.

For example,
```
module opt_check (input a , input b , output y);
	assign y = a?b:0;
endmodule
```
The above logic upon synthesis is infered as an AND gate on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/opt1.png)

```
module opt_check2 (input a , input b , output y);
	assign y = a?1:b;
endmodule
```
The above logic upon synthesis is infered as an OR gate with a NAND implementation on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/opt2.png)

```
module opt_check3 (input a , input b, input c , output y);
	assign y = a?(c?b:0):0;
endmodule
```
The above logic upon synthesis is infered as a 3 input AND gate on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/opt3.png)

```
module opt_check4 (input a , input b , input c , output y);
 assign y = a?(b?(a & c ):c):(!c);
 endmodule
```
The above logic upon synthesis is infered as a 2 input XNOR gate on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/opt4.png)

For optimisation fo a hierarchical structure with multiple different modules,

```
module sub_module1(input a , input b , output y);
 assign y = a & b;
endmodule


module sub_module2(input a , input b , output y);
 assign y = a^b;
endmodule


module multiple_module_opt(input a , input b , input c , input d , output y);
wire n1,n2,n3;

sub_module1 U1 (.a(a) , .b(1'b1) , .y(n1));
sub_module2 U2 (.a(n1), .b(1'b0) , .y(n2));
sub_module2 U3 (.a(b), .b(d) , .y(n3));

assign y = c | (b & n1); 


endmodule
```
The above logic upon synthesis is infered as a 2 input AND gate as an input to a 2-input OR gate on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/opt5.png)

For optimisation fo a hierarchical structure with multiple repeated modules,

```
module sub_module(input a , input b , output y);
 assign y = a & b;
endmodule



module multiple_module_opt2(input a , input b , input c , input d , output y);
wire n1,n2,n3;

sub_module U1 (.a(a) , .b(1'b0) , .y(n1));
sub_module U2 (.a(b), .b(c) , .y(n2));
sub_module U3 (.a(n2), .b(d) , .y(n3));
sub_module U4 (.a(n3), .b(n1) , .y(y));


endmodule
```
The above logic upon synthesis is infered as a 2 input AND gate as a direct connection of ground (logic 0) on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/opt6.png)

### Sequential Optimisations
The sequential logic optimisations techniques can be broadly classified into two categories:
* Basic Techniques: Sequential Constant Propagation
* Advanced Techniques: State Optimisation, Retiming, Sequential Logic Cloning etc.


**Examples of Sequential Constant Propagation**

```
module dff_const1(input clk, input reset, output reg q);
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b0;
	else
		q <= 1'b1;
end

endmodule
```
The above logic upon synthesis is infered as a D flip-flop with asynchronous reset on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/const1.png)
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_const1.png)

```
module dff_const2(input clk, input reset, output reg q);
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b1;
	else
		q <= 1'b1;
end

endmodule
```
The above logic upon synthesis is infered as a direct connection of VDD (logic 1) on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/const2.png)
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_const2.png)

```
module dff_const3(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b1;
		q1 <= 1'b0;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
The above logic upon synthesis is infered as two D flip-flop with asynchronous set and reset on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/const3.png)
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_const3.png)

```
module dff_const4(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b1;
		q1 <= 1'b1;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
The above logic upon synthesis is infered as a direct connection of VDD (logic 1) on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/const4.png)
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_const4.png)

```
module dff_const5(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b0;
		q1 <= 1'b0;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
The above logic upon synthesis is infered as a two D flip-flop with asynchronous reset on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/const5.png)
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_const5.png)

Below examples show the optimisations of unused states.

```
module counter_opt (input clk , input reset , output q);
reg [2:0] count;
assign q = count[0];

always @(posedge clk ,posedge reset)
begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
end

endmodule
```
The above logic upon synthesis is infered as a single D flip-flop instead of 3 flip-flops on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/copt1.png)
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_copt1.png)

```
module counter_opt (input clk , input reset , output q);
reg [2:0] count;
assign q = (count[2:0] == 3'b100);

always @(posedge clk ,posedge reset)
begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
end

endmodule
```
The above logic upon synthesis is infered as 3 flip-flops on optimisation.

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/copt2.png)
![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_copt2.png)

## Day 4
### Gate Level Simulation and Synthesis-Simulation Mismatch
As explained in previous sections, after following the steps to synthesis and obtaining the netlist, we can verify our netlist by perfoming Gate Level Simulation (GLS).
Synthesis-simulation mismatch refers to the differences between the behavior of a digital circuit as simulated at the Register Transfer Level (RTL) and its behavior after being synthesized to gate-level netlists. This can happen due to these main reasons:
* Missing Sensitivity List
* Blocking vs Non-blocking assignments
* Non standard verilog coding

### Examples
**ternary_mux**
```
module ternary_operator_mux (input i0 , input i1 , input sel , output y);
	assign y = sel?i1:i0;
endmodule
```
Netlist after synthesis:

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_eg1.png)

The waveforms before and after synthesis are as follows:

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/befaf1.png)

The waveforms are same which means there is no Synthesis-simulation mismatch.

**bad_mux**
```
module bad_mux (input i0 , input i1 , input sel , output reg y);
always @ (sel)
begin
	if(sel)
		y <= i1;
	else 
		y <= i0;
end
endmodule
```
Netlist after synthesis:

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_eg2.png)

The waveforms before and after synthesis are as follows:

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/befaf2.png)

The waveforms are different which means there is Synthesis-simulation mismatch.

**blocking_caveat**
```
module blocking_caveat (input a , input b , input  c, output reg d); 
reg x;
always @ (*)
begin
	d = x & c;
	x = a | b;
end
endmodule
```
Netlist after synthesis:

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/dot_eg3.png)

The waveforms before and after synthesis are as follows:

![alt text](https://github.com/aamodbk/iiitb_asic_course/blob/main/befaf3.png)

The waveforms are different which means there is Synthesis-simulation mismatch.

## Day 5
### If Case, For Loop and For Generate
**If Case and Case Constructs**
If is a conditional statement mainly used to create priority logic to execute particular pieces of code. Syntax for if-else loop is as shown below:
```
if (cond1) begin
	...
end
else if (cond2) begin
	...
end
else begin
	...
end
```
There is also a danger with using if-else conditions that if used with a bad coding style, it could be inferred as a latch. For example if the code below is synthesised, and if both the conditions evaluate to false, a hardware latch will be realised to retain the previous value and create the combinational loop.
```
if(cond1)
	y=a;
else if(cond2)
	y=b;
```

Similar to if-else conditions, case statement is used to implement multi-way branching based on the value of an expression.

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
