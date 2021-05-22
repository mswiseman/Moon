---
layout: post
title:  "DIY Laboratory Hardware for the non-engineer in plant sciences"
date:   Updated 2021-05-21
excerpt: "Resources to inspire creative problem solving"
project: true
tag:
- DIY 
- maker
- hardware
- hardwareX
- automation
comments: true
---

**I want you to stop and ask yourself: does your work involve protocols that are broken-down into simple, stepwise parts? Do you have processes that sequentially builds off of previous steps? Does your work involve gathering multiple types of environmental data at regular increments? If so, you might consider exploring DIY software and/or hardware for your laboratory.**

## Background

I made this website as a resource for anyone looking into DIY open-source hardware or software for their research. Broadly speaking, my research involves plant sciences and pathology; consequently, resources found here will initially be focused on hardware and software relevant to the plant sciences. However, lab hardware and software often transcend disciplines, so I hope you can find useful information regardless of your field. <br><br>I am **not** an engineer and thus I have tried to tread lightly in areas for which my terminology and/or understanding may not be accurate or thorough. Sometimes exploring a new skill or field can be frustrating or intimidating, especially early in the process; to overcome this, I encourage you to seek help from people who have more experience and from the many other resources available (videos, documentation, forums, etc.). Keep in mind: nobody is all-knowing and everyone has to start somewhere; alas, let's create a collaborative and supportive DIY movement together!

## Why DIY hardware/software?

If your lab is fortunate enough to be flush with funding, you may be asking: why bother building something myself when I can pay a company to do it for me? Great question. This may not be relevant for you. However, you may still find other benefits by learning how to build hardware and software yourself. Some benefits include:

* Improving accessibility to underfunded laboratories
* Creating customization and/or automation for repetitive tasks
* Improving intra- and inter-laboratory reproducibility
* Learning critical troubleshooting, coding, and electrical skills
* Building the socially-acceptable version of adult legos (okay, that's a joke)

## Resources \ [Back to top](#background)
**Interested in learning more? I hope so!** I encourage you to first look over the selected publications below as I believe they do an exceptional job with documentation and also show the wide range of applications for free open source hard and software in the laboratory. While purusing the published, peer-examples, think about similarities and differences between your work processes and the published work: does your research have similiar tasks or processes? If so, a good place to start is by learning more about the hardware and software implemented in the paper of interest. If electronic wiring and microcontrollers are new to you, you should then consider exploring a DIY kit (versatile kits [here](https://www.amazon.com/ELEGOO-Project-Tutorial-Controller-Projects/dp/B01D8KOZF4/ref=zg_bs_17441247011_1?_encoding=UTF8&psc=1&refRID=BBWW093183JGAM3DA6D6), [here](), and [here]()) before starting on a larger project - this will greatly reduce frustration later on by building troubleshooting skills in low stakes situations. 

* [Selected publications for inspiration](#selected-publications)
* [Peer-reviewed scientific resources](#peer-reviewed-scientific-resources)
* [Documentation for commonly used hardware](#hardware-documentation)
    * [Microcontrollers](#microcontrollers)
    * [Stepper drivers](#stepper-drivers)
    * [Environmental sensors](#environmental-sensors)
    * [Microprocessors/Mini-Computers](#mini-computers)
* [Exceptional YouTube tutorials](#youtube-tutorials)
* [Recommendations on where to purchase components](#purchasing-recommendations)
* [Local resources for Oregon State University](#local-resources)
* [Links to insightful reviews and commentary](#insightful-reviews-and-commentary)

---

## Selected publications \ [Back to top](#background)

[Highly-Customizable 3D Printed Peristaltic Pump Kit](https://www.sciencedirect.com/science/article/pii/S2468067221000316#f0010)<br/>
Keywords: peristaltic pump, fluid handling, cell culture, microfluidics

![Graphical Abstract](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/customizable_peristaltic_pump.jpg)
Other peristaltic pumps: [Jönsson 2020](https://www.sciencedirect.com/science/article/pii/S2468067220300249), [example2](http://link), [example3](http://link), [example4](http://link)

---

## Peer-reviewed scientific resources \ [Back to top](#background)
<img align="left" width="100" alt="HardwareX Logo" src="https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/hardwarexlogo.gif"> [HardwareX](https://www.journals.elsevier.com/hardwarex) is a peer-reviewed open access scientific journal dedicated to the open source design and construction of scientific instrumentation. The journal publishes science hardware shared under an open source hardware license. For DIY hardware, I believe HardwareX has the most detailed manuscripts that enable easier reproducibility. <br clear="left"/><br><br>

<img align="left" width="100" alt="Nature Scientific Reports Logo" src="https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/ScientificReportsandNatureLogo.png"> [Nature Scientific Reports](https://www.nature.com/srep/) is an open access journal publishing original research from across all areas of the natural sciences, medicine and engineering. To find manuscripts more likely to have DIY hardware, I would explore the tags [*lab-on-a-chip*](https://www.nature.com/search?q=lab-on-a-chip&order=relevance&journal=srep), [*biomedical engineering*](https://www.nature.com/search?q=biomedical%20engineering&order=relevance&journal=srep), or [*mechanical engineering*](https://www.nature.com/search?q=mechanical%20engineering&order=relevance&journal=srep). <br clear="left"/><br><br>

---

## Hardware documentation \ [Back to top](#background)

I've included direct links to the documentation of hardware commonly used in DIY free open source hardware. This field is rapidly evolving, so I imagine this section will change frequently. 

### Microcontrollers

Microcontrollers are the brains of hardware - they tell the other components what to do. They are best suited for simple repetitive tasks (such as activating a motor). I recommend choosing a microcontroller based on your power needs, programming language preference (generally C, C++, or micropython) power, but also based on the company's reputation and the available documentation. Speaking from experience: you will save yourself *a lot of frustration* if you work with a microcontroller that has thorough documentation and support (like the Arduino series). 

#### CNC Microcontrollers
Have a task that can be programmed and contained on an X, Y, Z system? You'll probably use computer numerical control (CNC). These microcontrollers have firmware that's adapted for and commonly used in CNC applications (CNC routers, 3d printers, liquid handlers, etc.):
* [Arduino Uno (8-bit)](https://store.arduino.cc/usa/arduino-uno-rev3)
* [Arduino Mega (8-bit)](https://store.arduino.cc/usa/mega-2560-r3)
* [Arduino Due (32-bit)](https://store.arduino.cc/usa/due)
* [Duet2 (32-bit)](https://www.duet3d.com/DuetWifi)
* [Duet3 (32-bit](https://www.duet3d.com/Duet3Mainboard6HC)
* [Smoothieboard (32-bit)](http://smoothieware.org/)

#### Tiny Microcontrollers
These are tiny microcontrollers are well-suited for wearable, lightweight, or limited space applications. 
* [Ardunio Nano (8-bit)](https://store.arduino.cc/usa/arduino-nano)
* [Raspberry Pi Pico](https://www.raspberrypi.org/products/raspberry-pi-pico/)
* [Seeeduino XIAO](https://www.seeedstudio.com/Seeeduino-XIAO-Arduino-Microcontroller-SAMD21-Cortex-M0+-p-4426.html)


### Microcontroller firmware
Firmware is essentially permanent software that is programmed to microcontrollers. You will need to change the firmware (or write your own) to adapt it for your application; consequently, it's wise to familiarize yourself with the available resources, formatting, and limitations of various firmware packages. Firmware is typically written in C, C++, or Micropython. The software component of DIY hardware *can be challenging*, **but** there are tools, such as integrated development environments (IDE), that can make customizing firmware fairly straightforward. Not familiar with IDE? If you have used R-Studio or Jupyter Notebook, then you have used IDEs for the R and Python, respectively. [Here's](https://www.youtube.com/watch?v=ana1mFFMHIk) a nice overview of IDEs.

#### Most commmon microcontroller firmware packages
* [Marlin](https://marlinfw.org/)
    * [Compatible 8/16/32-bit boards](https://marlinfw.org/docs/hardware/boards.html)
* [grbl](https://github.com/grbl/grbl)
    * Compatible with Arduino Uno Stack, Arduino Nano Stack, MKS-DLC, Mega 2560 Stack, and others
* [MicroPython](https://micropython.org/download/)
    * Compatible with Pyboard v1, STM32 boards, Raspberry Pi Pico, WiPy, TinyPICO, and others 
* [RepRap](https://reprap.org/wiki/RepRap)
    * [Compatible 8/16-bit boards](https://reprap.org/wiki/Category:8/16-bit_board)
    * [Compatible 32-bit boards](https://reprap.org/wiki/Category:32-bit_board) 
* [Smoothieware](https://smoothieware.org/)
    * Compatible with all RepRap boards 

### Stepper drivers
Explain stepper drivers

* [1](1)
* [2](2)
* [3](3)

### Environmental sensors
Explain environmental sensors

* [1](1)
* [2](2)
* [3](3)

### Mini-computers
Technically speaking, mini-computers (aka microprocessors) are not microcontrollers as they can handle multiple tasks at once. These are best suited for software-heavy applications.
* [Raspberry Pi](https://www.raspberrypi.org/)

---
## YouTube Links \ [Back to top](#background)
There are endless tutorials and informational videos on YouTube, but some are more helpful than others. I found these to be particularly helpful with my adventure into DIY hardware. 
* [How to build a 3D printer, The Ultimate Guide](https://youtu.be/qub5chyIQ0s)
    * This video is helpful understanding any type of CNC hardware, not just 3D printers
* [Breadboarding & Prototyping for Electronics, Arduino & Raspberry Pi](https://youtu.be/Y3Kx2RlLXsY)
* [Schematic Diagrams & Symbols, Electrical Circuits - Resistors, Capacitors, Inductors, Diodes, & LEDs](https://youtu.be/Dl1gFBNa0Ik)
* [How to wire a cheap power supply](https://youtu.be/Ls-6BeLHbA0)
* [DIY Dremel CNC #3 electronics, software and firmware (Arduino, aluminium profiles, 3D printed parts)](https://youtu.be/xfQ0YosR6us)
* [How To Wire It! Stepper Motors](https://youtu.be/GgfgWU0bpHk)
* [Raspberry Pi Pico - Control the (I/O) World](https://www.youtube.com/watch?v=Zy64kZEM_bg&t=247s)
    * The Raspberry Pi Pico is the first microcontroller from Raspberry Pi (released February 2021). 
    * As far as I know, it's the only microcontroller that can be programmed with MicroPython (also C and C++)
---

## Insightful Reviews and Commentary \ [Back to top](#background)
* [A Review of Raspberry Pi Usage in Scientific Research](https://www.raspberrypi.org/blog/raspberry-pi-a-versatile-tool-for-biological-sciences/)
* [Smoothieware vs. Marlin: Which Firmware is Better](https://www.3dprintingspot.com/post/smoothieware-vs-marlin-which-firmware-is-better)

---

## Questions or comments?  \ [Back to top](#background)

I'd love for this to be a collaborative process, so please [send me](michele.wiseman@oregonstate.edu) your questions/suggestions/comments or post them to the comments below (let's all be kind humans though, okay?). 

---

## Updated \ [Back to top](#background)
This page was last updated 05/21/2021. *Disclosure statement: I do not benefit financially from any of the links on this page - I choose to not to have affiliate links to reduce bias and try to remain objective.*
