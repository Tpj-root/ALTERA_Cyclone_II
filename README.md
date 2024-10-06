# ALTERA_Cyclone_II
ALTERA FPGA, Cyclone II: From Basics to Mastery






1. Introduction to FPGA and Cyclone II
   - What is an FPGA?
     Field-Programmable Gate Array (FPGA) is a semiconductor device that can be programmed to perform a wide range of tasks.
   - What is ALTERA Cyclone II?
     Cyclone II is a low-cost FPGA by ALTERA (now Intel), commonly used in academic and industrial projects.
   
   Key Concepts:
   - Learn basic digital logic: Logic gates, flip-flops, counters, and multiplexers.
   - Understand FPGA architecture: Configurable logic blocks, I/O blocks, and routing.


## PDF

[Cyclone II Device Handbook, Volume 1](src/D_sheet.pdf)

[Product Marking Information](src/mark_info.pdf)

[Pin Information for the Cyclone II EP2C5 Device](src/pinout.pdf)




2. Setting Up the Environment
   - Quartus II Software: This is the development tool for programming Cyclone II. Download and install Intel Quartus II.
   - Installation on Debian:
     tar -xvf quartus_linux.tar
     cd quartus_linux
     sudo ./setup.sh
   - Ensure Cyclone II device support is installed.


## Device and Operating Environment Details: 

##  lsb_release -a

```
Distributor ID:	Debian
Description:	Debian GNU/Linux 11 (bullseye)
Release:	11
Codename:	bullseye
```

[Debian]()
<p align="center">
  <img src="src/neofetch.png">
</p>



## Software download 

### Intel® Quartus® II Web Edition Design Software Version 13.0sp1 for Linux

[link](https://www.intel.com/content/www/us/en/software-kit/711790/intel-quartus-ii-web-edition-design-software-version-13-0sp1-for-linux.html)


<table border="1"><tr><td>Size: 4.5 GB</td></tr><tr><td>sha1: 2b110eff0d544bcda4013e265f6feaa507482357</td></tr><tr><td>FileName: Quartus-web-13.0.1.232-linux.tar</td></tr></table>



How to install

```
cd Quartus-web-13.0.1.232-linux
./setup.sh
```

## Quartus Web is built using 32-bit software, so some 32-bit libraries are required.



```
sudo apt-get install libpng12-0:i386
```


The libpng12 software is not available in Bullseye, I plan to build it for i386.

Download [link](https://sourceforge.net/projects/libpng/files/libpng12/)


<table border="1"><tr><td>Filename : libpng-1.2.59.tar.gz</td></tr><tr><td>SHA1 : 6debaeea473a4a9e8b53ad203b8b14399a14f437</td></tr><tr><td>MD5 :8909478bf85d80395f80e925bd79c0f8</td></tr></table>




### Source to build 

```
sudo apt update
sudo apt install build-essential gcc-multilib

tar -xvf libpng-1.2.59.tar.gz
cd libpng-1.2.59
./configure --prefix=/usr/i386 --host=i386-linux-gnu
make
sudo make install
sudo ldconfig
```



### Other package lists needed for dependency

```
sudo apt-get install libfreetype6:i386
sudo apt-get install libsm6:i386
sudo apt-get install libxrender1:i386
sudo apt-get install libfontconfig1:i386
sudo apt-get install libxext6:i386


```

### How to run Quartus

```
export PATH=$PATH:/home/sab/altera/13.0sp1/quartus/bin
./quartus
./quartus --64bit
```


This is the directory where you can find installed libraries:

When you build your own library, all related libraries will be located here:


```
/usr/local/lib
```





## tips 

```

Installation directory [/home/sab/altera/13.0sp1]: 

----------------------------------------------------------------------------
Please specify the directory where Quartus II Web Edition (Free) 13.0.1.232 will 
be installed

Installation directory [/home/sab/altera/13.0sp1]: 

----------------------------------------------------------------------------
Select the components you want to install

Quartus II Web Edition (Free)  [Y/n] :Y

Quartus II Web Edition (Free)  - Quartus II Software (includes Nios II EDS) (4424MB) : Y (Cannot be edited)

Quartus II Web Edition (Free)  - Quartus II Software 64-bit support (1090MB) [Y/n] :Y

Quartus II Web Edition (Free)  - Quartus II Help (627.9MB) [Y/n] :y

Quartus II Web Edition (Free)  - Devices [Y/n] :y

Quartus II Web Edition (Free)  - Devices - Arria II (482.8MB) [Y/n] :n

Quartus II Web Edition (Free)  - Devices - Cyclone II/III/IV (615.2MB) [Y/n] :y

Quartus II Web Edition (Free)  - Devices - Cyclone V (751.8MB) [Y/n] :n

Quartus II Web Edition (Free)  - Devices - MAX II/V, MAX 3000/7000 (9.1MB) [Y/n] :n

ModelSim-Altera Starter Edition (Free) (3547.1MB) [Y/n] :y

ModelSim-Altera Edition (3547.1MB) [y/N] : n

Is the selection above correct? [Y/n]: y


Summary:
  Installation directory: /home/sab/altera/13.0sp1
  Required disk space:  10304 MB
  Available disk space: 11386 MB


[Desktop Entry]
Type=Application
Version=0.9.4
Name=Quartus II 13.0sp1 (64-bit) Web Edition
Comment=Quartus II 13.0sp1 (64-bit)
Icon=/home/sab/altera/13.0sp1/quartus/adm/quartusii.png
Exec=/home/sab/altera/13.0sp1/quartus/bin/quartus --64bit
Terminal=false
Path=/home/sab/altera/13.0sp1


```




3. Basic Quartus Project Setup
   - Create a new project in Quartus II.
   - Select Cyclone II as the target FPGA device.
   - Design a simple AND gate using Verilog or VHDL.
     module and_gate (input A, input B, output Y);
         assign Y = A & B;
     endmodule
   - Synthesize, simulate, and program your FPGA.

4. Programming Languages for FPGA
   - Verilog and VHDL are the most common hardware description languages (HDLs) for FPGA design.

5. Flashing the Cyclone II FPGA
   - Compile the design in Quartus and upload the compiled .sof file to the FPGA using the Quartus Programmer tool.

6. Intermediate Concepts:
   - Finite State Machines (FSMs): Essential for controlling digital systems.
   - Memory in FPGA: Learn about Block RAM (BRAM) and Distributed RAM.
   - Using IP Cores: Quartus provides pre-built IP Cores to integrate into designs.

7. Using I/O Peripherals
   - Interface with LEDs, 7-Segment Displays, and Buttons.

8. Advanced Topics
   - Embedded Processors, DSP Blocks, and High-Speed I/O.

9. Simulation and Debugging
   - Use Quartus’ simulation and SignalTap tools for debugging.

10. Mastering FPGA
   - Implement complex digital systems like Image Processing Pipelines, Signal Processing, and Custom Processor Design.

Key Tools for ALTERA Cyclone II FPGA:
   1. Quartus II – Development environment.
   2. ModelSim – Simulation and testing.
   3. USB-Blaster Programmer – Programming the FPGA.

Helpful Resources:
   - Intel FPGA University Program: University Program
   - ALTERA (Intel) Documentation: Documentation



   - https://www.intel.com/content/www/us/en/support/programmable/support-resources/devices/cyclone-ii-support.html

