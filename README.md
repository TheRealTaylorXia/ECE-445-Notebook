# ECE-445-Notebook

## 3/24
Seeing as this was our first meeting after break, today's agenda was mainly concerned with consolidating any work we'd done. Jay and I compared our code for getting the IMU working. Jay had figured out how to get readings running a circuitpython script which made readibility much nicer. I showed him my code which inclucded a section for calibration and changing some of the chip's registers to enable a low pass filter so as to reduce errant readings due to passible motor wobbling. These were added into the circuitpython code. Mitchell began to work on some of the steppor motor code and got one to move a little bit. We all had classes to get to at this time so we decided to meet again this weekend to finish.

## 3/26
Today's meeting was primarily involved in getting the steppor motors to work with the Teensy Board. Jay's purchase of the voltage regulator modules came in, so him and I soldered pins on those and tested them. Eventually, we tuned the potentiometer so that it outputs around 5 volts with an input of 18 volts. Mitchell and I also got the motors to work. We finished up the meeting discussing our PCD design.
