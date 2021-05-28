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

## Plan

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

Once I had built a few trivial electronics projects, I felt confident to take on the project. This is a classic case of "the less you know, the easier you think it will be." It was also the middle of a global pandemic, so... I was longing for a project to help enable my research and get my mind off the death and despair of the world. 

My plan was to follow David Florian's Ottobot design as I thought he had made several inivative improvements over the OT-1 (and let's face it, it's also because he offered to help over zoom). After getting his design to work, I was then planning on simplifying wiring, building a UV light enclosure, and then trying my hand at building a multichannel syringe-pump to use as the floating head (with eventual plans of making a complete PCR system with thermalcycler, centrifuge, and robotic arm).

## Build

*Note: This will be long and is not intended as something for you to build along with; it's intended to be lessons for those interested in building a similar machine. Consequently, I've emphasized and tried to explain the mistakes I made. I'm hoping to put together a polished build video in the future.*

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


**This was one of the many mistakes** I made during the build: trying to build the floating head while attached to the X-axis. If you take on this build, you should fully complete the floating head and then build the X-axis.  That way you don't have to undo/redo things a bunch of times. You can also see the comical mismatching or total absence of many screws. This was not intentional. By not following David's BOM exactly, I had miscalculated the number of screws and turns out you can't find M5 screws locally. Alas, I had to order more from Opentrons and shipping was slow during the pandemic, so many of the upcoming pictures also have missing/mismatching screws. 

![Assembly4](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/assembly4.png)

Still mismatching screws 😆 , but I had assembled much of the floating head and X axis here. Eventually I'll mill a gantry plate - just need to find a mill locally. Now I needed to commit to buying the pipette actuator. This was night a light decision as this was the most expensive part of the build (~$200). I looked on eBay for months... but no non-captive stepper motors that would produce the same force and microstepping we needed. Alas, I ordered it and then had to step away until it arrived. 

Pardon the mess... it's a reality when you have a thousand small pieces and no real work space. 
![Assembly5](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/IMG_4295.jpg)

In the meantime, I thought I'd try to get the motors moving, as per Dr. D Flo's suggestion. **This is when I really started realizing how little I know.** I bought the TMC2660 breakout board stepper drivers and I didn't know the first thing about breakout boards or stepper driver (yes, I literally had to google all of those words).  I tried putting jumper cables through the holes in the breakout board on a breadboard but the wouldnt get a good connection. Alas, I realized I need to [solder "headers" onto these boards](https://www.bakke.online/index.php/2017/05/18/soldering-headers-to-boards/). I also realized that these boards were too wide for a breadboard, so I literally hacked a breadboard to make them work (see [here](https://hackaday.com/2018/08/27/the-solution-to-oversized-dev-boards-a-literal-hack/). 

I'm still not great at soldering, but I've learned [flux](hhttps://www.amazon.com/MG-Chemicals-milliliters-Pneumatic-Dispensing/dp/B00425FUW2/) makes it so much easier. 
![Soldering](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/soldering.gif)

Alas, I spent many, many hours (and at least two Arduino Dues) trying to David's incredibly complex wiring to work. I have so much respect for his wiring skills, but after ~20 or so hours troubleshooting, I was pretty disheartened. I had A4988 stepper drivers on hand and I could get them to move my nema 11, but I couldn't get anything to move with the TMC2660BOBs. I still don't have an answer to this. Feel free to shoot me feedback. 

Here's my first major failure. I directly wired my 24V power supply to my Arduino Due. Poof! RIP. Newbie mistake. Most microcontrollers can't handle more the ~3V.
![Burned Out](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/burnedout.jpg)

Alas, I made sure to not to wire high voltage directly through the my next Arduino Due. 
![New board](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/newboard.jpg)

But, no matter what I did, I couldn't get any of the example Arduino files to run the motors. I tried uploading different firmware, I tried the Arduino IDE, I tried pronterface, etc. I checked the power draw to the motors (with multimeter) and it was only around 1.2V. This didn't make sense. These motors needed more power than that. Alas, it had to have been something in my wiring (perhaps an improper ground?). I wired and re-wired and tried not to lose my mind. **I decided that I needed to step away for a bit to regroup and then try to tackle the project with simpler wiring and software.**

So, with David's help, I explored options to simplify the wiring and software. I was interested in finding a chip with integrated stepper drivers as this would remove ~30 wires; unfortuntely, not many chips have integrated stepper drivers that can run the very powerful Nema 23 stepper motors we had ordered for the project (they're max power intake is 3A). I was also interested in finding a chip that could run the Opentrons software (which runs on Smoothieware). David's software is great, but at the time, it only worked on windows and I didn't own a windows computer.

That left me with very few options, especially for someone who doesn't know enough to circumvent the pitfalls of each option.
* [Smoothieboard v 1.1](http://smoothieware.org/smoothieboard-v1)
This wouldn't be able to provide full power to the Nema 23s, but could work. 
* [Smoothieboard v 2.0](https://www.kickstarter.com/projects/arthurwolf/smoothieboard-v2)
This would be the perfect solution, but had not yet been released. I did try playing with PCB design for a minute though to see if I could get it working... then I realized I was definitely not an electrical engineer. 
* [Duet2](https://www.duet3d.com/DuetWifi)
This doesn't run on Smoothieware, though had the right stepper drivers. 
* [SKR 1.4](https://www.amazon.com/BIGTREETECH-Controller-Compatible-With12864LCD-5TMC2209/dp/B082QYYFVX/)
This would work, but had poor documentation. 

Alas, I ordered the SKR board and a Smoothieboard v 1.1. The Smoothieboard took eons to arrive, so I gave an A effort to get Otto running with the SKR board and TMC5160 stepper drivers. Ultimately, I was overwhelmed by the amount of changes necessary in the firmware and the physical changes necessary with the TMC5160 stepper drivers. This would probably be a great setup for someone with my experience. In the meantime: I tried to go for low hanging fruit to maintain morale. I replaced all the mismatching screws, designed a fun new face-plate, printed cable management clips, and started designing an enclosure. 

![Faceplate Design](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/IMG_4195.jpg)

Once the Smoothieboard arrived, I flashed the [OT-one firmware and config to it.](https://github.com/Opentrons/smoothie-config/tree/master/v2.0.0/one_standard). I then went through the arduous process of changing all the motor connections. AGAIN. Why can't these boards just share a common connector? Fortunately, the smoothieboard ships with the necessary connectors, so it's just a matter of cutting the old wires, stripping, crimping, and inserting in the connector. 

To get an idea of Smoothieboard setup, you can see this diagram from Arthur Wolf (co-creator). It's the original in the picture, but you get the idea: lots of setup is required. 
![Smoothieboard](https://live.staticflickr.com/7263/7832149516_76d367a105_b.jpg)

Fortunately, Smoothieboard has very thorough documentation and a large community that offer help. **This was the magic answer.** I needed to choose a board that had good documentation and lots of help. I needed to ask for and accept more help. Once I did this, everything started working flawlessly-ish. This is probably a lesson I should have learned from my previous yearly feedback from Dave (my adviser), 'Michele, you're doing great, but your life would be easier if you asked for help earlier and more frequently.' 🤦‍♂️ Perhaps too stubborn for my own good.

![Working in the lab](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/lab.jpg)

[GIF of the motor moving!](https://drive.google.com/file/d/1Re4YQ6gIKHAVTnT0YlTY11NGimF6cE45/view?usp=sharing)

Alas, once I had **finally** achieved movement from the motors, I went about wiring up my Ottobot. I used [3d printed cable clips](https://www.thingiverse.com/thing:3396905) (and [here](https://www.thingiverse.com/thing:4426587)), [drag chains](https://www.thingiverse.com/thing:1001437), and zip ties for cable management. Eventually I might put some sleeves over the cables too, but for now it's okay. There's some great tips on wiring [here](https://smoothieware.org/how-to-wire).

[Cable Management](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/cablemanagement.jpg)

I decided to also wire up a computer fan as the stepper drivers were quite hot in the demo run (not pictured). Eventually I'll probably swap the on-board drivers out for high power stepper drivers, but they seem to work okay for now. We'll see if how the compare to the actual opentrons robot once I get the pipette installed (I'm building a sturdier pipette holder). Overall, the wiring is just **so much easier**. I did have to jumper the two Y-axes together though (following the OT-one firmware to tell me where), but that was pretty simple. 

[Wiring](https://raw.githubusercontent.com/mswiseman/mswiseman.github.io/master/assets/img/wiring.png)




















