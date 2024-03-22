---
title: "Exploring a computer's hardware"
description: "Diving into some detailled explanations of a computer's motherboard and other hardware components"
pubDate: 'Nov 10 2023'
updatedDate: 'Nov 13 2023'
heroImage: '/motherboard.png'
---

### Who is this for? 
During my bachelor's days, I used to believe that understanding a computer's architecture, hardware, and circuits was an insurmountable task, that I would need additional diplomas and extensive studies just to gain a basic understanding. However, if you, dear reader, are reading this and feeling similarly overwhelmed, I want to reassure you: that's not the case! There are numerous articles, short courses, videos, and other resources available, all dedicated to making knowledge more accessible to people from all backgrounds. This article represents my personal contribution to this effort. I hope you find it enjoyable and useful! 

### Context
If you've ever sat in front of a computer, you've likely noticed that it consists of more than just a single component. You may have heard terms like "RAM," "SSD," or even, if you're well-informed, "CPU." But what do these terms mean? What roles do these components play? How do they come together to make an entire computer function? And perhaps most importantly, why should you care? In this article, I'll do my best to answer all of these questions through a high-level, illustrated, and not overly technical explanation.

 It's worth noting that I will focus on the fundamental components of a PC, understanding that specifications may vary depending on the model and type of computer. Additionally, there will inevitably be discrepancies with laptops. I may delve into these specifics in a future article, but for now, let's focus on learning to stand before attempting to walk or even run.

### The basic theory
Can you tell the difference between your laptop and your little cousin's calculator? Besides the price, the fundamental distinction lies in their functionality. The calculator serves a singular, predefined purpose: to perform calculations. We refer to this as a **Fixed Program Computer**. Your laptop, on the other hand, offers a more possibilities, so many possibilities, everything you want actually! Highly customizable and easily reprogrammable, it can execute a diverse range of tasks, store data, and run applications. Introduced by John von Neumann, this type of computing architecture is known as a **Stored Program Computer**. 

Von Neumann outlined three fundamental components constituting such a computer, which we'll refer to as units. These units include the ***Memory Unit*** for data and program storage, one or more ***input/output devices*** facilitating interaction, and the ***Central Processing Unit*** (CPU), which serves as the intermediary between these units. 

Let's do the analogy to an Amazon distribution center —albeit with less evil connotations. 

It requires physical support, a warehouse storing packages and/or the inventory of the client's orders, much like the Memory Unit. 
Input/output devices function akin to distribution trucks, facilitating the delivery between the warehouse and the clients. 
Finally, none of it would be possible without a management department which, like a CPU, is divided into three teams. The _Control Unit_ oversees the reception of client orders, processes data, and maintains the distribution center's operations, the _Arithmetic and Logic Unit (ALU)_ handles complex calculations to optimize production and distribution, and the last one, the _Registers_ will assist by storing and providing quick access to essential information, so that less people need to go all the way down to the warehouse. 


insert SCHEMA here :) 

While the CPU's complexity extends far beyond this brief overview, delving into its intricacies would require something like 250 [pages](https://link.springer.com/book/10.1007/b102502) of highly technical explanations. Perhaps a topic for another time! 

This short introduction lays the groundwork for further understanding of the article. Let's begin with the real deal shall we? 

### The motherboard
Most of the components in a PC are connected through a printed circuit board (PCB) or circuit board. Within this structure, many components are either plugged in or soldered onto the circuit, and depending on their functionality, they can interact with each other. There are many different manufacturers on the market, including popular ones like Asus and high-quality ones like Gigabyte and MSI, which you may have heard of. Regardless, most motherboards have a common basic structure:

- CPU slots: These are integrated circuit slots, housing electrical components responsible for providing physical support for the CPU and an interface to the board. 
- Memory slots : These slots are where the system's Random Access Memory (RAM), or simply memory, is installed.
- Storage connector : These provide interfaces for the hard drive, also known as storage, a device capable of containing large amounts of data but with slow access. There are two main types of connectors: SATA and NVMe. 
- The Basic Input/Output System BIOS : This is a non-volatile memory chip (flash memory) that stores firmware. 
- Chipset : The Northbridge Chipset forms an interface between the CPU, memory, and storage, while the Southbridge Chipset connects peripheral elements to the motherboard. 
- The Real Time Clock RTC : This is used for tracking the time of different system events, such as the creation of a file, which will then include a "time stamp."
- Power connector : This consists of either 20 or 24 pins for plugging into a power supply and distributing electrical (DC) power through the circuit to the CPU, chipset, memory, and expansion cards.
- Connectors for expansion cards and peripheral devices : These include graphic card connectors and USB ports etc. 

_NOTE: Work on progress! I still have to simplify the following sections. sorryyyy_

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


_Note: SATA and PCIe can both use M.2 connector but only PCIe can use NVMe (Non-Volatile Memory Express) connector. PCIe has a better performance and speed than SATA_

### Sockets and connectors

Sockets and connectors, including the VRM (Voltage Regulator Module) with heat sinks, play a crucial role in facilitating connections between various hardware components.


### Power Supply 
- Main transformer to reduce the voltage. Isolation between:
    - Primary side high voltage 
    - Secondary side lower voltage
- Control PCB (Process Control Block): checks the output voltage and sends adjustments to the switching power transistor on the primary side
--> Important thing for the power supply: filter input voltage and generate output voltages according to the hardware component's needs. 


### GPU
The GPU is a powerhouse responsible for rendering graphics. Here's an overview of its   components:

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


##### DRAM  

The DRAM (Dynamic Random-Access Memory) is a type of memory that can access any location in memory with roughly the same time delay, allowing for high densities at a low cost. Depending on the model, DRAMs usualy come on groups of 8 connected to a DIMM (Dual-Inline Memory Module), a small circuit board plugged to the motherboard and that allows communication with the CPU through memory channels. 

On the DIMM, DRAM chips are organized in a Hierarchical way:

DIMM > Rank > Chip > Bank > Row > Column. 

The DRAM chips, at the highest level or organization within the DIMM, are grouped on "ranks". Chips on the same rank share address and command buses, and will be controlled at the same time, but will still provide different data. 

Inside each chip, there is a set of banks. They are arrays that operate independently of each other, so they can be in different phases of a data access/refresh cycle. Each bank can be accessed simultaneaously by the chips within a rank, allowing a better distribution of reading/writing tasks. 

A bank is organized in rows and cells. Rows can be seens as groups of memory cells (1T1C using transistors and capacitors), which can be accessed when a row activation command is received.  All chips with access the same row on the same bank. The column is then the smallest addressable unit of memory. An specific memory address can be accessed thanks to the row decoder, the column decoder and the data buffer of every bank. 

DRAM is mostly used because of its rapid write/read capacity, but it can't be used for big amouts of data to be stored permanently. 


### Conclusion
Understanding a computer may not be easy, but it's not impossible either. With this short guide, you now have the basics. Go forth and continue learning!


### Sources

https://www.youtube.com/watch?v=d86ws7mQYIg&t=909s

DRAM: 

https://www.allaboutcircuits.com/technical-articles/introduction-to-dram-dynamic-random-access-memory/

http://thebeardsage.com/dram-nomenclature-explained/

https://www.youtube.com/watch?v=ntq2y-d5-NU

SSD: 


