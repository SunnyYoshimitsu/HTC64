# Y!6502
Think Ben Eater's 6502 but modified....a modified BE6592...the Y!6502....

I modified this computer to have 2 VIA chips instead of just one since I think having more GPIO will allow it to be used as a more conventional microcontroller. Also I changed the memory layout and add a larger RAM. So the memory layout ended up being inverted to Ben's, 32k of RAM and 16k of ROM. There's an expansion slot in the middle designed to take a stock Ben Eater's GPU with its !DMA config or any other peripherals you want. The expansion slot is mapped to A000 - BFFF. 

Note there's a VGA output and associtated resistors, however there are no GPU to drive it. This is for the expansion slot. I am planning a "modified" BE6502 GPU that uses a dual port RAM so that the CPU can run at 100% capacity. Now this computer is basically everything that the BE6502 is except for the GPU but ofcourse you don't have to populate everything. 

I'm porting Wozmon to this modifed BE6502 since the UART is in a different place and it does support a keyboard. I will update this repo as soon as I'm done with it. 

If you have any question or ideas please don't hesitate to hit me up! I am an active user in the r/beneater subreddit. 
Profile: https://www.reddit.com/user/YoshimitsuSunny

Memory Layout: 
	Note: each section is 8k in size
0000 - 1FFF: RAM
2000 - 3FFF: RAM 
4000 - 5FFF: RAM 
6000 - 7FFF: RAM
8000 - 9FFF: DDRAM 
A000 - BFFF: Peripheral
A200 - UART
A400 - A40F: I/O Timer 1
  Reg A: GPIO
  Reg B: P/S 2
A800 - A80F: I/O Timer 2
  Reg A: GPIO
  Reg B: GPIO
C000 - DFFF: ROM (lower address) 
E000 - FFFF: ROM (higher address) 