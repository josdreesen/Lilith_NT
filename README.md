# Lilith_NT

This database documents my attempt to recreate the 1980's ETH Lilith Modula-2 workstation. Both hardware and software is to be docuemnted here.

The actual CPU will be identical to the original machine, shortcuts will be made to avoid some of the original problems :
- The disk was either a Honeywell-Bull 10Mb cartridge drive, or a 15Mb  MFM drive, controlled by a WD1001.
- NEW -> This is to be replaced by a DOM-disk with ATA interface.
- The original ha 4 PCB's with each 32 4116-type DRAM-chips, for a total of 128K 16bit words.
- NEW -> a single PCB will hold 16 256Kx4 chips, for a total of 1M 16bit words.
  Other characteristics will remain the same ( i.e. write access in 16bit words, read access in either 16bit of 64bit words)
- NEW : DIN41642 connecdtors will replace the original, hard to find and expensive 1.125" spaced board edhe connectors.

Lilith-NT hardware consists of 8 PCB's, all newly designed in a more compact format :

DPU : a MC6802 based debugging aid. This takes over the main busses in the system, allowing direct access to the hardware.
      Original schematic, slightly newer memory chips, new board layout.
      Not needed in normal operation of a Lilith.

ALU : the actual CPU, consisting of 4 AMD2901 bitslices, hardware stack and a 16bit barrel shifter.
      Original schematic with a new board layout.

MCU : microcode unit. Contains the microprogram that controls the bitslices, also has the microcode sequencer and clockgen circuitry.
      Original schematic with a new PCB layout, but now also has the memory address registers, originally in the CDP board.

IFU : instruction fetch unit. Also contains boot eprom. Original schematic with a new board layout.

DRAM: main memory, consisting of 16 4x256K DRAMs. Updated design of the original, using much denser chips. 
      Also contains the Dataregister which was originally in the CDP board.
      
DSP : Display unit / Videocard. Original schematic with a new board layout.      

IOP : IO board : new design, new PCB combining keyboard & mouse interface. 
      Also contains 2 serial channels, ATA / DOM disk, floppy interface and RTC chip.
      
Mainboard : carrries the above mentioned boards in dedicated slots.
            New design, using DIN-connectors instead of the cardedge connectors to reduce cost and increas reliability.
                        
      

The subdirectories, one for each pcb,  contain a .zip file with the gerbers, a .pdf with the schematic, a rendering of the PCB
and the Kicad Database itself.
