---
layout: post
title:  "Building a Modular Automated Liquid Handling System"
excerpt: "From conception to execution"
feature: https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/wiring.jpg
date: 2021-05-26
tag:
- DIY 
- maker
- hardware
- Ottobot
- Opentrons
comments: true
---

# This is a work in progress, please come back

## I do a lot of repetitive things in the name of science

And if you're here, I'm guessing you do too. One process I've probably done 10,000+ times is setting up a polymerase chain reaction (PCR). This winter, before my comparative genomics class, I was talking for my professor, Dr. Aaron Liston, about how many plates I needed to run just to get pre-liminary data for my *MLO* work(~50). He suggested I look into robotics. **Of course**! How had this maker not considered that? So, I scoured all sects of internet and came across numerous examples of scientists all of the world building their own liquid handlers (each with varying levels of documentation). 

### Opentrons
![Opentrons](https://opentrons.com/static/OT1_app-6bf1e6dce7a7ab1597563f2737975d8a.jpg)
Opentrons was probably the first fully open automatic liquid handler. They debuted back in 2015 with a [kickstarter campaign](https://www.kickstarter.com/projects/932664050/opentrons-open-source-rapid-prototyping-for-biolog). Their original OT-one design has X, Y1, Y2, Z, and A axes (A is for the pipette, which is driven by an non-captive nema stepper motor). 
* [Opentrons 3D model](https://sketchfab.com/3d-models/otone-liquid-handling-robot-0db23019eee5445f9fcebc73fa510a25)
* [Opentrons software](https://github.com/Opentrons)

### Ottobot
![Ottobot](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/otto.webp)
Ottobot was created in 2020 by Vanderbilt PhD student, David Florian. He roughly based his design off of the Opentrons OT-1 (X, Y1, Y2, Z, and A axes), but added additional limit switches and lasers to check for successful loading of pipette tips. He also included the very powerful (albeit not as easy to work with) TMC2660 stepper drivers which allowed him to harness the full power of the Nema 23 stepper motors. Opentrons had to reduce current in their firmware as their stepper drivers weren't able to support the powerful motors. 
* [Ottobot](https://openliquidhandler.com/)
* [Manuscript discussing Ottobot](https://www.nature.com/articles/s41598-020-70465-5)

### Other liquid handlers
[Pipette Jockey's OT-One](http://pipettejockey.com/2018/01/03/making-a-opentrons-compatible-liquid-handling-robot/)
Pipette Jockey does an incredible job at rebuilding the OT-One. Check out his other builds too. 

[OpenLH](https://www.youtube.com/watch?v=r-m2pXBq76A)
This liquid handler uses a robot arm coupled with a syringe pump. 

[Open Workstation](https://www.sciencedirect.com/science/article/pii/S2468067220300614)
Full work station for cell culturing. They bought the Opentrons pipette though, which is why I didn't follow their plans (I can't drop $4k on a pipette). 

[EvoBot](https://www.mdpi.com/2076-3417/10/3/814/htm)
Evobot is like the OT-one but uses a syringe pump. It's an impressive build. 

[Public Lab Pipetting Robot](https://publiclab.org/notes/JSummers/12-29-2018/a-diy-pipetting-robot-for-biochemistry-applications-part-1-hardware)
Impressive public build. 

## Idea

Alas, I was inspired by all of the available plans and by the "free and open-source hardware" (FOSH) movement. In theory, by building your own automatated liquid handler, you can save money, customize your equipment, have more reproducible data, and expand access to scientific equipment globalling (by reducing cost). 

![Thought Process](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/thoughtprocess.png)

So, I tracked down one of my favorite [YouTubers](https://www.youtube.com/channel/UCJ10renzLSd4cJEn-C2e_Tw) (who is also the inventor of Otto) and told him my plans. He was pumped and offered to help when he was able to. This is what I love about the maker movement: everyone wants you to succeed. This became quickly apparent to me after witnessing the effort that strangers made while trying to help me (message boards, neighbors, fab labs, library, Dr. D Flo, etc.). 

## Necessary tools

First I needed to acquire the necessary tools, and, quite frankly, learn a little more about electronics. I've been a maker my whole life, but mostly with wood. I've only dabbled in electronics with my van build, occassional repairs, and house projects. I'm definitely not proficient and often jerry-rigging things. 

![Van](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/IMG_9623(1).JPG)

Alas, I wanted to do things right this time around, so I picked up the necessary (and optional) tools, tried a few Arduino kit tutorials, and practiced my crimping. I also built up some misplaced confidence by assembling my own 3d printer (from a kit). 

![Necessary tools](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/tools.png)

Necessary tools for this project:
* Metric allen wrenches
* Metric open wrenches
* Needle nose pliers 
* Tape measure
* Precision calipers
* Crimpers
* Wire strippers
* M5 tap
* Multimeter
* Small screwdriver set

Potentially optional
* Soldering iron (can avoid soldering with [connectors](https://3daddict.com/3d-printer-wiring/))
* Solder
* Solder remover
* Extra soldering iron tips
* Helping hands
* Clamps
* Corner squares
* 3D printer (check your local resources first)

## Plan 
Once I had built a few trivial electronics projects, I felt confident to take on the project. This is a classic case of "the less you know, the easier you think it will be." 

My plan was to follow David Florian's Ottobot design as I thought he had made several inivative improvements over the OT-1 (and let's face it, it's also because he offered to help over zoom). After getting his design to work, I was then planning on simplifying wiring, building a UV light enclosure, and then trying my hand at building a multichannel syringe-pump to use as the floating head (with eventual plans of making a complete PCR system with thermalcycler, centrifuge, and robotic arm).

## Build

So, I found cheaper alternatives to the components found in Otto's [Bill of Materials](https://github.com/DrD-Flo/OTTO/blob/master/assets/download/OTTO-BOM-7-1-20.xlsx). In the end, this a was a mistake as some of the alternatives I ordered were not compatible (ex. the lead screw and couplers) and it ended up costing me a lot more time and money. 

Here are most of the materials for the build. Not picture: aluminum extrusion for the bed and frame, pipette actuator, pipette, additional 3d printed components. 

![Materials](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/materials.png)

As pandemic "luck" would have it, I had a spare room open, so I moved the build into the spare room. 

![Assembly1](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/assembly1.png)

One of the essential parts to building a CNC machine is ensuring it's square, so I used clamps and eventually two squares to make sure everything was squared nicely. 

![Assembly2](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/assembly2.png)

Slipping in the T-nuts so I can secure the bed. You can see the Ottobot Fusion 360 file open in the background. This is when I realized I needed to tap the aluminum extrusion... something I had never heard of. Tapping means threading a predrilled hole. The aluminum extrusion I ordered from OpenTrons had been predrilled, but not tapped. Alas, I went to harbor freight and bought a very terrible tapping kit. Do not buy it. Go buy a quality M5 tap - it'll save you money, time, and blisters. 

![Assembly3](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/assembly3.png)

I found tapping to be difficult. I suggest practicing on something if possible. If you have a vice, wrap your aluminum extrusion in a wash cloth (to protect it) and tighten it down. This will help immensely. Once everything was tapped, I secured the T plates with 8mm M5 screws and thus secured Otto's bed. 


![Tapping](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/IMG_4179(2).gif)


**This was one of the many mistakes** I made during the build: trying to build the floating head while attached to the X-axis. If you take on this build, you should fully complete the floating head and then build the X-axis.  That way you don't have to undo/redo things a bunch of times. 






