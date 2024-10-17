# ALTERA MAX II

ALTERA MAX II programming : From Basics to Mastery




**Requirement:**

Alter Max || EPM240T100C5N
Data cable : A-Male to Mini-B
Altera USB-Blaster 
Computer with Quartus Software Version 13.0sp1 for Linux




Device and Operating Environment Details:

istributor ID:	Debian
Description:	Debian GNU/Linux 11 (bullseye)
Release:	11
Codename:	bullseye


Source to build : [Tips](README.md)



**Setting up the PLD**


Connect the USB cable to the USB-Blaster, 
then connect the JTAG to the USB-Blaster.



**Creating the File**


EP2C5T144C8N
[FPGA_Help_Video](https://www.youtube.com/watch?v=xppagENez_Y&ab_channel=MilanKarakas)


EPM240T100C5N
[MAX II_Help_Video](https://www.youtube.com/watch?v=0gz4n1Xvcyc&ab_channel=Kronch)







run
/home/sab/altera/13.0sp1/quartus/bin/quartus --64bit





Create project with name

max_2_test



family & device and Bpard settings


family : MAX II

EPM240T100C5N

--> NEXT  ---> FINISH





new --> block& schematic file


then double click in the grid



find logic gate

lib --> primitive --> logic --> nor2(gate)




search Name input get the what u need function

click ctrl pin copy to many

get the line draw to click ctrl

then save the .bdf file (schematic file)

after that 

--> start compilation 

output show the sucess ()


pin planner --> 


click to round  then goto right side Node name :
 --> pin_name1 --> PIN2
 --> pin_name2 --> PIN4
 --> pin_name3 --> PIN6







how to upload svf file in max ii



openFPGALoader -c usb-blaster -m .svf



sab@SH4D0W6:~/altera/max2/output_files$ openFPGALoader -c usb-blaster -m max2_test.svf
empty
write to ram
Read error: -7
JTAG init failed with: Unknown device with IDCODE: 0x2f2e2f2e (manufacturer: 0x797 (), part: 0x79 vers: 0x2









need to build






PR






Add support for the max II board. TESTED

board: Alter Max II EPM240T100C5N

NOTES:

    Known to work with SVF files





/home/sab/altera/max2





