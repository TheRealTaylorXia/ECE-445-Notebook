# ECE-445-Notebook

## 2/9
Started my lab notebook so this'll be the first entry of mine. Had a meeting with Jay and Mitchell today to go over our project proposal and have that ready to submit today. Overall looks pretty good. I personally did the work on explaining which parts we picked and why. 

## 2/13
The meeting today was mainly about preparing for our first regular TA meeting tomorrow. We decided to order our parts today so we can start prototyping and breadboarding as soon as possible as well as asking our TA on any recommendations on parts. Some things we can hold back on, but we can definitely order the motors and Teensy microcontroller right now. 

## 2/14
First of the regrular TA meetings we'll have with our TA. Most of what we talked about was about our design document, how that should be made, and our parts. We then set up a meeting this weekend to go over and get a first draft of our design document ready.

## 2/19
We had a work meeting at Grainger today to just knock out some of the design document. I did a lot of the requirements and verifications as well as some of the portions in the overall design that explained what parts we were using and why we decided to use them. We got a lot of work done, but decided to stop there and continue tomorrow. After that, we should be finished and able to send in our design doc to be reviewed while we prepare for the design review presentation.

## 2/28
We had our design review today, didn't go as smoothly as hoped for to be honest. We found out that we were missing a fair amount of things from our design document. Fortunately, we still got a decent final grade on our presentation. Our TA handed us a rubric with most of the missing information which we will be working on for the next couple of meetings.

## 3/06
Today's meeting was primarily forcused on working on our revised design document and preparing that for submission. Jay also got the second Teensy he ordered, so I came with a USB to micro-USB cable and testing our some example programs on that. I mainly focused on refining our requirements and verifications, Mitchell on the cost and ethics section, and Jay on the block diagram.

## 3/07
Had our TA meeting today. Main objective was to jsut check our design document revision and make sure everything looks ok to submit. Aftwards, we dicussed what parts we had aquired and how soon we wanted to get a PCB. We decided previously that we didn't want to order a PCB from the first batch, namely because we hadn't even gotten to breadboarding yet and we wouldn't be able to get our hands on it until after spring break anyway.

## 3/21
Me and Jay compared our IMU code to eachothers. Jay and I unforunately seemed to have caught some kind of virus over break however, so we just sent the code to each other. Jay went with the approach to use circuitPython to run his IMU while I just used C code. I have to say, circuitPython looks a lot cleaner especially when it came to the I2C communication protocol. Either way, we have both sets of code on hand in case we decide to go one way or the other with how we program the entire system.

## 3/23
Both me and Jay are still sick, so no meeting in person for us. We may be able to meet up tomorrow once we both feel better, we'll just have to see how things turn out. We were still able to get a lot of work done though, mainly related to initial thoughts on the PCB design and finalizing our design document. After looking it over, we all decided it was good to submit. Otherwise, we organized to meet tomorrow in the morning to go over the mirade of things we worked on and consolidate our work.

## 3/24
With this being the first in person meeting we had in a while, today's agenda was mainly concerned with consolidating any work we'd done. Jay and I compared our code for getting the IMU working. Jay had figured out how to get readings running a circuitpython script which made readibility much nicer. I showed him my code which inclucded a section for calibration and changing some of the chip's registers to enable a low pass filter so as to reduce errant readings due to passible motor wobbling. These were added into the circuitpython code. Mitchell began to work on some of the steppor motor code and got one to move a little bit. We all had classes to get to at this time so we decided to meet again this weekend to finish.

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
Had to skip going to the lab yesterday due to an exam for another class, though it seems while Jay and Mitchell were testing some things our Teensy board fried out. Fortunately, we bought multiple backups so I was able to bring my working one. Jay and Mitchell also bought some extras as well in case this happens again in the future. Today, I brought the new teensy and we soldered it to the PCB board for testing all 4 motors. It seems there was some kind of problem with out PCB though; two of the motor drivers and the teensy microcontroller seem to have burned out in the process of testing. We're in the process of desoldering those components, and Jay and Mitchell are redesigning a PCB.

## 4/17
I wrote the first of the PID code we would be using yesterday and me and Jay had the chance to try it out in the lab today. Other than chaning around some of the motor pins and directions, now begins the arduous task of tuning the algorithm. Unfortunately, we don't have enough motor drivers to run all four motors at the moment as some previously burned out the last meeting. I currently tuned the PID for two motors moving one axis but we'll need the other drivers and use the battery to test all four. Other than that, we also tested some code to get the motors to respond to the IMU turning. That seems to have gone pretty well but it's still a little choppy, will need to do more work on it later.

## 4/20
In a previous meeting, Mitchell and Jay were able to run my IMU plus motor code and got it to work on all four motors, so now all motors react properly to the IMU turning around. I also did a lot of work on the PID algorithm today while Jay helped desolder a lot of compnents. Most of my time was spent tuning the PID constants. It really doesn't help that the IMU's angle is strange in that it rolls over from 360 to 0 degrees and back again, making calculations within the code more difficult.

## 4/21
Me and Jay worked some more on the PID code today. Jay introduced some checks within the code which look at the absolute value of the angle and error value and adjust the amount the motor moves by accordingly. Overall happy with the state the code is in currently, now we just need to take the IMU and actually put it on the balance tray and test out how that works. I'm assuming we'll likely have to retune the PID somewhat. Me and Mitchell had the idea that instead of placing the IMU underneath the tray and making it harder for ourselves we could just tape it on top of the board but place it upside down thus simulating it being underneath.

## 4/22
Got the IMU attached to the board. Honestly, not too bad of a result on first try. There did need to be some adjustments to prevent oscillations and steady state error, but by the end of the meeting everything seems to work pretty well. Good thing too with the final demo being just a few days away. Jay also did a lot of work on our new PCB and getting the components onto there. We purchased extra sets of chips for everything just in case something burns out again. We will need to test it all tomorrow to see if truly all runs together. It seems everything is coming together very nicely, we'll have a finished product soon.

## 4/23
Great news is the PCB does work! This time we implemented the PCB very slowly, using the multimeter to check every component to make sure it actually was getting power and that it wasn't getting too much. Mitchell's revised 3d print of the volcano also came in which we used to great effect at keeping the entire board steady. By the end of the meeting, we attached everything together and ran it all on the Milwaukee battery and it all ran very well. We're all really happy and very prepared for tomorrow's demo.

## 4/24
The final day, everyone's really excited. Me and Jay did some final tuning on the PID code to have the balance try balance out a bit faster. We saved a backup copy of our current code just in case; don't want to do anything rash and then not have a way to go back. Fortunately, the change seems good and did help the balance tray out quite a bit. It's also good Jay and Mitchell thought to purchase even more backups of the motor drivers after we got our new PCB, because as luck would have it one of the motor drivers really did burn out; these things just give up whenever they feel like it. Jay was able to quickly run up to the lab and grab a replacement, and we spent the rest of the time waiting for our demo tuning the potentiometer on it.
