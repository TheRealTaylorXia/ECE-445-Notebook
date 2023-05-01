# ECE-445-Notebook

## 3/24
Seeing as this was our first meeting after break, today's agenda was mainly concerned with consolidating any work we'd done. Jay and I compared our code for getting the IMU working. Jay had figured out how to get readings running a circuitpython script which made readibility much nicer. I showed him my code which inclucded a section for calibration and changing some of the chip's registers to enable a low pass filter so as to reduce errant readings due to passible motor wobbling. These were added into the circuitpython code. Mitchell began to work on some of the steppor motor code and got one to move a little bit. We all had classes to get to at this time so we decided to meet again this weekend to finish.

## 3/26
Today's meeting was primarily involved in getting the steppor motors to work with the Teensy Board. Jay's purchase of the voltage regulator modules came in, so him and I soldered pins on those and tested them. Eventually, we tuned the potentiometer so that it outputs around 5 volts with an input of 18 volts. Mitchell and I also got the motors to work. We finished up the meeting discussing our PCB design.

## 3/27
We met in the lab today to finish discussing some of the design decisions with the PCB. Noteably, we decided that the IMU was going to be connected to the PCB through three wires coming directly off of the board. There were also some issues with tracing the PCB in AutoCAD but Mitchell and Jay had fixed that issue by the end of the meeting. 

## 4/4
We had another meeting with our TA. Progress is looking good; Mitchel completed the assembly for the physical part of the food tray earlier last week and me and Jay got a chance to get a good look at it today. This also means our progress on the PID code can begin. Jay and I had done a little pre-research into this looking into the IMU DMP and seeing if that can be useful. We tinkered with the motors some more after the meeting, but me and Jay agreed we're both pretty busy this week and will begin development on the PID algorithm later.

## 4/9
Very good progress, we were able to make the motors move and actually manuver the balance plate today. Jay and I went to the lab early to test out all the motors but it we ran into the problem of the lab power supply units limiting the amount of output power. We had to move to using the Milwaukee 18V battery by plugging two wires into the positive and negative ports on it. We were still having some problems making the motors move smoothly, however. Afterwards, Mitchell and Jay were able to mess around with the potentimeters on the motor drivers and eventually get them to move better.

## 4/11
Found a slight problem with the IMU code we had origninally planned on using today. It turns out the code that we were running returned the rate at which the IMU was turning, not the actual angle reading. This results in the IMU's values going to 0 if you held it in the same spot for a while rather than actually changing depending on it's orientation. We spent the meeting changing around this code which effectively ended up just involving changing which registers we were reading from. We're hoping to test all 4 motors moving and getting the motors to react to the IMU readings next.

## 4/13
Had to skip going to the lab yesterday due to an exam for another class, though it seems while Jay and Mitchell were testing some things our Teensy board fried out. Fortunately, we bought multiple backups so I was able to bring my working one. Jay and Mitchell also bought some extras as well in case this happens again in the future. Today, I brought the new teensy and we soldered it to the PCB board for testing all 4 motors. It seems there was some kind of problem with out PCB though; two of the motor drivers seem to have burned out in the process of testing. We're in the process of desoldering those components, and Jay and Mitchell are redesigning a PCB.
