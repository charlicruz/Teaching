# Timer Tutorial

This is a 555 timer based project for new electronics team members to wet their feet in the world of hardware design and prototyping, *without needing to do any coding!*

The goal is simple, have new members design an LED blinker using a 555-timer chip to flash at about 0.5 Hz. Ideally they start by reading and digesting the datasheet for the 555 timer (included as a PDF in this repository) and working their way to a circuit board in KiCad with some prototyping inbetween so they get experience with all stages of a circuit bring up.

In addition to the 555 datasheet, a complete KiCad project for this project is also included. **New members should make their own projects from scratch** as part of this exercise but this can be distributed to late joiners or used as a reference when lecturing about KiCad. 

### New Member Prepartion

**New members shouldn't really be expected to prepare for this project** *(at least for the first (prototyping) part)*. All prototyping materials should be prepared by the head of electronics in advance. Luckily nothing is needed for this that isn't usually laying around McCaul already, except for perhaps some 555 chips.

For teaching/learning KiCad it is helpful for each member to have their own laptop with the latest version of KiCad pre-installed so they can follow along instead of just watching. This can easily be "homework" if the project is borken between multiple sessions.

# The Project

The task for this project is simple, create a blinker that could be used as an indicating light for when a bike needs to turn. Just like with a car, the blinking needs to be perceptible so neither too fast nor too slow, roughly a second of the LED being on followed by a second of it being off is adequate.

To accomplish this we are going to use a 555 timer chip, arguably the most produced integrated circuit (IC) ever and a common gateway chip to hobby electronics. It can be used many different ways so one must read the documentation on the chip in the form a datasheet and then determine how to proceed with the design.

Once familiar with the chip and a rough design is settled on, we can embark on the rest of the electronics design process! Ideally with a nice flashy prototype by the end of it.

## Process

This project is meant to be reflective of the general electronics development process. In general the following steps are completed in roughly this order, not too disimilar to the flow of a majority of engineering projects:

1. **Determining the scope of a project.** _What are our inputs/outputs? What can/can't we use? Etc._
2. **Research into parts.** _Reading data sheets, reviewing reference designs, seeing other people's work._
3. **Building [breadboard] prototypes.** _Building circuits with non-perfect/non-exact components (e.g. no 1253.7 Ohm resistors), learning about component polarity, __verifying connections__!_
4. **Assessing circuit performance.** _Determining expected behaviour, using measurement equipment like multimeters and oscilloscopes._
5. **Iterating on design as needed.** _Adjusting component values, re-reading documentation, verifying calculations._
6. **Transcribing circuit schematic into Electronics Design Assistant (EDA).** _Start operating KiCad schematic tool._
7. **Designing circuit board in EDA.** _Using more KiCad, selecting footprints, introduction into design for assembly/manufacturing._

Going through all these steps in a single session, especially when starting out is unlikely without it feeling rushed or a marathon of a session. Consider doing the prototyping in one large session with a shorter follow-up session for the EDA portion, this also gives them time to install KiCad at home in advance of the KiCad session. _(Protip: it is much easier when teaching larger groups to have everyone at a similar stage in the process.)_
