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

Alas, I was inspired b


![Thought Process](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/thoughtprocess.png)

## Necessary tools

![Necessary tools](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/tools.png)
