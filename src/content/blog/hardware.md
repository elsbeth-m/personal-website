---
title: 'Exploring a computers hardware'
description: 'Diving into some detailled explanations of a computers motherboard and other hardware components'
pubDate: 'Nov 10 2023'
heroImage: '/motherboard.png'
---

### CPU basics

At the heart of every computer lies the Central Processing Unit (CPU), a powerhouse responsible for executing instructions and driving the entire system. Let's delve into its basic components:



- Integrated Heat Spreader for heat dissipation
- Integrated circuit (IC) or die 
    - The IC resides on a printed circuit, facilitating communication with the motherboard.
    - Cores: Execute tasks such as fetching, decoding, renaming, allocating, and dispatching instructions.
    - Has 8 to 10 billions transistors 
    - Features a shared L3 cache for efficient data access.
    - Utilizes a Ring Interconnect for internal communication.
    - Includes an Integrated Graphics Processor.
    - Memory Controller for managing data flow to and from the RAM
    - System Agent Platform I/O : communicates with chipset and motherboard

The CPU operates at 1.32V, supplied by the Voltage Regulator Module (VRM), generating substantial heat. To counteract this, the CPU is equipped with various coolers, some employing pumps to circulate hot and cold liquid.


### Chipset basics
The chipset, an integrated circuit beneath a heat sink, is crucial for managing various components connected to the CPU's system agent. 
Whereas the CPU interact with a few components like the DRAM, displays, the GPU and some SSD (solid-state drive), the chipset manages : 
- Ethernet and Wifi data
- data flowing to and from hard drives plugged into the SATA ports (Serial Advanced Technology Attachment). SATA is what allows every storage-related component to connect to the motherboard
- some PCIe (Peripheral Component Interconnect express) slots
- Peripherals: keyboard, mouse, speakers, microphone...
- BIOS support : for Intel this is Management Engine Firmware, PTT(an implementation of TPM) and others. 



_Note: SATA and PCIe can both use M.2 connector but only PCIe can use NVMe connector. PCIe has a better performance and speed than SATA_

### Sockets and connectors

Sockets and connectors, including the VRM (Voltage Regulator Module) with heat sinks, play a crucial role in facilitating connections between various hardware components.


### Power Supply 
- Main transformer to reduce the voltage. Isolation between:
    - Primary side high voltage 
    - Secondary side lower voltage
- Control PCB (Process Control Block): checks the output voltage and sends adjustments to the switching power transistor on the primary side
--> Important thing for the power supply: filter input voltage and generate output voltages according to the hardware component's needs. 


### GPU
The GPU is a powerhouse responsible for rendering graphics. Here's an overview of its components:

- GPU IC: 
    - 11.8 billion transistors
    - 6 graphic clusters
    - 28 streaming multiprocessors 
        - each one has 128 cores (CUDA core)
        - each CUDA core has floating point unit and integer unit, and a result queue.
    - shared L3 memory cache among graphic clusters 
    - Memory controllers connecte to the VMRAMs
    - PCIe interface to connect to the CPUk
- VRAM
- VRM 
- heat sink, ports (DP, HDMI), PCIe interface, power connectors.

### Memory and drives 

##### DRAM  

The DRAM (Dynamic Random-Access Memory) is a type of memory that can access any location in memory with roughly the same time delay, allowing for high densities at a low cost. Depending on the model, DRAMs usualy come on groups of 8 connected to a DIMM (Dual-Inline Memory Module), a small circuit board plugged to the motherboard and that allows communication with the CPU through memory channels. 

On the DIMM, DRAM chips are organized in a Hierarchical way:

DIMM > Rank > Chip > Bank > Row > Column. 

The DRAM chips, at the highest level or organization within the DIMM, are grouped on "ranks". Chips on the same rank share address and command buses, and will be controlled at the same time, but will still provide different data. 

Inside each chip, there is a set of banks. They are arrays that operate independently of each other, so they can be in different phases of a data access/refresh cycle. Each bank can be accessed simultaneaously by the chips within a rank, allowing a better distribution of reading/writing tasks. 

A bank is organized in rows and cells.
##### SSD

##### HDD


### Sources

https://www.youtube.com/watch?v=d86ws7mQYIg&t=909s

https://www.allaboutcircuits.com/technical-articles/introduction-to-dram-dynamic-random-access-memory/

http://thebeardsage.com/dram-nomenclature-explained/
