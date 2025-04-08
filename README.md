# FPGAmini
# VSD_Squadron_FPGA_Projects
This repo contains four FPGA-based projects showcasing real-time UART communication, LED control, and sensor data acquisition. Designed using Verilog, Yosys, and NextPNR, running on the VSD Squadron Mini FPGA board



##  About the Board

### **Board Specifications**
🔹 **FPGA Chip**: Lattice UltraPlus ICE40UP5K (5.3K LUTs)  
🔹 **Memory**: 1Mb SPRAM, 120Kb DPRAM, 4MB SPI Flash  
🔹 **General Purpose I/O (GPIO)**: 32 accessible pins  
🔹 **Connectivity**: FTDI FT232H USB-to-SPI for programming & debugging  
🔹 **Multipliers**: 8 DSP multipliers for arithmetic operations  
**[View the Datasheet](https://www.vlsisystemdesign.com/wp-content/uploads/2025/01/VSDSquadronFMDatasheet.pdf)** 
  

---




#  Setup & Installation



***


### **Navigate to the Specific Project**

Each project has its own directory. Navigate to the project you want to work on:

Example:

    
    cd VsdSquadron_mini_fpga_uart_loopback

To view available files:

    
    ls
    

***


### **Clean Previous Builds**

Before starting a new build, clean old files using:

```sh
   sudo make clean
```

This removes any previous bitstream files.

***


### **Build the FPGA Bitstream**

To **synthesize the design and generate the bitstream**, run:

    sudo make build

This will execute:

- **Synthesis (Yosys)**
- **Place & Route (NextPNR)**
- **Bitstream Generation (IceStorm)**

***


### **Flash the FPGA**

Once the bitstream is built, upload it to the FPGA using:

```sh
    sudo make flash
```
This command programs the **VSD Squadron Mini FPGA board**.

***
