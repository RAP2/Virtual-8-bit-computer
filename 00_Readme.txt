8_Bit_Comp_Digital_Works describes the architecture of an 8 bit computer. It uses the software Digital Works to create all the virtual components.

References: 
Building an 8-bit breadboard computer! by Ben Eater:
https://www.youtube.com/playlist?list=PLowKtXNTBypGqImE405J2565dvjafglHU
Digital Computer Electronics by Albert Paul Malvino
Digital Works 95 Ver 2.04 David John Barker, later versions are available for download from the internet to run the dwm files. 

Rationale
In 2020, based on the references above, I designed a 8-bit virtual computer using Digital Works 95. This year 2025, I look at this 8-bit virtual computer and I have no idea how it works. This frightens me! Am I suffering from dementia? I intend to refresh my memory and investigate the workings of the virtual computer by documenting the details. I am not an expert in this field but I wish to increase and consolidate my knowledge.

Description
01_comp_with_program_28_add_14.dwm 
This file shows a glimpse of a virtual computer loaded with the program to add two numbers, 28 and 14. To turn off the grid, click View, uncheck Show Grid. To increase clock speed, click Circuit, Clock Speed, select 10 Hz. Run the program. The LEDs will start flickering and after a while, the result (28 + 14 = 42) is shown on the display. Please be patient as the virtual computer runs at 10 Hz maximum. 
How is the computer designed? I will attempt to explain the workings of the individual components.

01_comp_with_program_28_add_14.jpg 
This file shows the graphics for the program.

01_comp_with_program_28_add_14.map 
This file is the program code that you can reload into the 16 x 8 RAM just in case the program is corrupted. Click on RAM, to reload the program.

02_RAM.dwm
This file shows how a program stored in a RAM (random access memory device) is displayed on a BUS (digital highway that connects all devices in the computer). You can manually change the memory address inputs to display the data bits stored in the address.

02_RAM.jpg 
This file shows the graphics for the program.

03_RAM_clock_binary_counter.dwm
Instead of manually changing the memory address inputs, a clock and a 4-bit binary counter is used to display the program machine code sequentially. Humans count numbers using the decimal number system (1, 2, 3, 4...). Computers count using the binary number system (binary counter: 0000, 0001, 0010, 0011, 0100...1111), hence the term binary counter. View the program in steps.  

03_RAM_clock_binary_counter.jpg
This file shows the graphics for the program.

04_Program_Counter.dwm
In some programs, we need to branch (Jump) and execute instructions stored at other memory addresses. The Program Counter comprises a clock and a 4-bit special binary counter (from Ben Eater's video). Test the different functions: Clock (on/off), CE(Count Enable Increment), Reset(clear) and Jump(Program Counter In).   

04_Program_Counter.jpg
This file shows the graphics for the program.
    
05_Memory_Address_Register.dwm
This file shows a 4-bit special register* (from Ben Eater's video) with Enable data out always on. When MI In (Memory Address In) is on, it will load the memory address (on the BUS) onto the 4-bit register and save it there. It is not sent to the 16 x 8 RAM yet. However for this 4-bit register, the Enable data out is always on. Hence the memory address is sent to the RAM immediately.  

05_Memory_Address_Register.jpg
This file shows the graphics for the program.

06_Program_Counter_Out_Register.dwm
This file shows a 4-bit special register (from Ben Eater's video) with Load data in always on. The 4-bit CO Program Counter Out Register will load the data (from the Program Counter) onto the register (since the load data in button is always on) and save it there. The data is not sent to the bus yet. When the CO (Program Counter Out) is on, the data (that was saved on the 4-bit register) will be placed onto the BUS.

06_Program_Counter_Out_Register.jpg
This file shows the graphics for the program.

06B_Special_register_and_counter.dwm
This file lets you experiment with the load and enable functions of the special registers (4-bit/8-bit) and counters (4-bit).

06B_Special_register_and_counter.jpg
This file shows the graphics for the program.

07_Combine_04_05_06.dwm 
This file shows the workings of the combined devices: RAM, Program Counter, Memory Address Register and Program Counter Out Register. All these devices are connected to the BUS. Binary data are 'In' or 'Out' on the bus. We have to ensure that no two devices output data to the bus at the same time, as this will cause bus contention. The devices' Load data in and Enable data out must be synchronised correctly at the rising edge of each clock pulse.   

07_Combine_04_05_06.jpg
This file shows the graphics for the program. 

07_Combine_04_05_06.map 
This file is the program code that you can reload into the 16 x 8 RAM just in case the program is corrupted. Click on RAM, to reload the program.

08_comp_with_program_load_output.dwm
In 07A_Combine_04_05_06.dwm, you have to manually key in the memory address to view the program codes. 08A_program_load_output.dwm shows how the program codes are decoded using an instruction decoder (1K x 16 ROM) and a counter to trace the steps to carry out the instructions (16 x 16 ROM). The file shows how the number 28 is loaded into the 'A' Register. The micro codes for each opcode are shown.

08_comp_with_program_load_output.jpg
This file shows the graphics for the program.
 
08_comp_with_program_load_output.map
This file is the program code that you can reload into the 16 x 8 RAM just in case the program is corrupted. Click on RAM, to reload the program.

08_comp_with_program_load_output_explanation.jpg
This file shows the graphics detailing the steps for the 08_program_load_output.dwm. 

09_display.dwm
This file shows how the bus binary data is displayed on the LED display as decimal number. 

09_display.jpg
This file shows the graphics for the program.

09_display_2.dwm
This file shows how negative numbers are represented in computers. 

09_display_2.jpg
This file shows the graphics for the program.

09_display_3.dwm
This file shows how data stored in ROM lights up the 7 segments LED display. 

09_display_3_A.jpg
This file shows the graphics for the program.

09_display_3_B.jpg
This file shows the graphics for the program.

09_display_3_C.jpg
This file shows the graphics for the program.

09_display_ROM_0_1_2_decoder.map
This file contains the 16 x 8 ROM data for the LED lighting up the 100's places of the LED display.

09_display_ROM_coded.map
This file contains the 256 x 16 ROM data for the LED lighting up the 10's and 1's places of the LED display.

09_display_ROM_coded.txt
This file contains the ROMs data for the 7 segments in LED display. 

10_addition.dwm
This file shows how computer adds two 8-bit data. 

10_addition.jpg
This file shows the graphics for the program.

11_comp_with_program_28_add_14_explanation.dwm
This file shows how a virtual 8-bit computer works. The example program is add two numbers (28 and 14) to give 28. 

11_comp_with_program_28_add_14_explanation.jpg
This is the accompanying picture to explain how a virtual 8-bit computer works.
The Flag Register In will be explained later in 17_comp_with_program_count_up_and_down.dwm.

11_comp_with_program_28_add_14_explanationB.jpg
This file shows the graphics for the program.

11_Instruction_Decoder.map
This file contains all the instruction opcodes and microcodes of the virtual computer.

11_Instruction_Decoder.txt
This file contains in printed text, all the instruction opcodes and microcodes of the virtual computer.

12_subtraction.dwm
This file shows how computer subtracts two 8-bit data. 

12_subtraction.jpg
This file shows the graphics for the program.

13_comp_with_program_3_subtract_1.dwm
This file shows the computer program 3 subtract 1. 

13_comp_with_program_3_subtract_1.jpg
This file shows the graphics for the program.

13_comp_with_program_3_subtract_1.map
This file is the program code that you can reload into the 16 x 8 RAM just in case the program is corrupted. Click on RAM, to reload the program.

13_comp_with_program_3_subtract_1_explanation.jpg
This file explains how the program works.

14_comp_with_program_Fibonacci.dwm
This file shows the computer listing for the Fibonacci series. 

14_comp_with_program_Fibonacci.jpg
This file shows the graphics for the program.

14_comp_with_program_Fibonacci.map
This file is the program code that you can reload into the 16 x 8 RAM just in case the program is corrupted. Click on RAM, to reload the program.

14_comp_with_program_Fibonacci_explanation.jpg
This file explains how the program works. 

14_comp_with_program_Fibonacci_explanation2.jpg
This file explains how the program works. 

15_comp_with_program_2_multiply_3.dwm
This file shows how to multiply 2 numbers, x and y without a conditional branch instruction (attributed to Matthew Kudzin).  
There is a new instruction STA (store a value in 'A' Register). You may like to figure out how the program works yourself or skip this program and go on to 16_comp_with_program_count_up.dwm

15_comp_with_program_2_multiply_3.jpg
This file shows the graphics for the program.

15_comp_with_program_2_multiply_3.map
This file is the program code that you can reload into the 16 x 8 RAM just in case the program is corrupted. Click on RAM, to reload the program.

15_comp_with_program_2_multiply_3_Matthew Kudzin.jpg
This is the note by Matthew.

16_comp_with_program_count_up.dwm
This file explains how the carry flag halt the program when a number is greater than 255.

16_comp_with_program_count_up.map
This file is the program code that you can reload into the 16 x 8 RAM just in case the program is corrupted. Click on RAM, to reload the program.

16_comp_with_program_count_up_explanation.jpg
This file explains how the program works in overview.

16_comp_with_program_count_up_explanation_details.jpg
This file explains how the program works in detail.

16B_comp_with_program_count_down.dwm
This file explains how the zero flag halt the program when a number is below zero.

16B_comp_with_program_count_down.map
This file is the program code that you can reload into the 16 x 8 RAM just in case the program is corrupted. Click on RAM, to reload the program.

16B_comp_with_program_count_down_explanation.jpg
This file explains how the program works in overview.

16B_comp_with_program_count_down_explanation_details.jpg
This file explains how the program works in detail.

17_comp_with_program_count_up_and_down.dwm
This program combines 16_comp_with_program_count_up.dwm and 16B_comp_with_program_count_down.dwm. The program counts up from 0, then counts down from 255. This cycle is repeated indefinitely. The program makes use of the Flags Register, flags, CF(carry flag) and ZF(zero flag). 

17_comp_with_program_count_up_and_down.map
This file is the program code that you can reload into the 16 x 8 RAM just in case the program is corrupted. Click on RAM, to reload the program.

17_comp_with_program_count_up_and_down_details.jpg
This file explains how the program works in detail.



