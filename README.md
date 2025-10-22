# Following-Nymeria
It is about creating a meaningful solution to a problem many pet owners face. By combining technology with compassion, the animal tracker not only showcases the potential of micro:bits and coding but also demonstrates how innovation can directly improve everyday life A portable tracker using just a microbit, a computer and a battery!. This project logs, displays, and transmits acceleration data using the BBC Micro:bit’s built-in accelerometer and radio module. It can be used to track motion, detect movement strength, or communicate acceleration data wirelessly between Micro:bits.



## Overview

The script performs three main functions:
1. Logs acceleration data (`x`, `y`, and `z` axes) to the Micro:bit’s datalogger every second.  
2. Displays total acceleration strength on the LED screen every five seconds.  
3. Sends acceleration data wirelessly using the Micro:bit’s radio module on group **18**, so that another Micro:bit can receive and display the same data.

Technologies Used

Microbit V2.0

---

## How It Works

### 1. Data Logging
- The Micro:bit logs acceleration values on the X, Y, and Z axes every 100 ms (0.1 seconds).  
- Data is stored in the datalogger for later export via the MakeCode editor.

```python
datalogger.log(
    datalogger.create_cv("x", input.acceleration(Dimension.X)),
    datalogger.create_cv("y", input.acceleration(Dimension.Y)),
    datalogger.create_cv("z", input.acceleration(Dimension.Z))
)

#### 2. Display Acceleration

The Micro:bit shows the overall acceleration strength on its LED screen every five seconds:

basic.show_number(input.acceleration(Dimension.STRENGTH))
basic.pause(5000)

##### 3. Radio Transmission

The Micro:bit sends its acceleration strength over the radio to other Micro:bits on radio group 18.

A receiver Micro:bit can listen and display this incoming data.

radio.set_group(18)
radio.send_number(input.acceleration(Dimension.STRENGTH))

###### Setup Instructions

Open MakeCode / MicroPython editor at https://makecode.microbit.org/

Create a new project.

Copy and paste the provided code into the editor.

Flash the code to your Micro:bit.

Load the same project onto a second Micro:bit to receive data.

####### Testing

Shake or move the transmitting Micro:bit — the acceleration strength should appear on both:

The transmitting Micro:bit’s screen

The receiving Micro:bit’s screen

Data points will also be recorded in the datalogger and can be viewed in MakeCode or downloaded as a .csv file.

###### Requirements

2 × BBC Micro:bits (for send + receive)

MakeCode or MicroPython environment

Battery pack 

String or Ribbon

(Optional) Collar or Harness

###### Set Up

Download the code onto respective microbits

Attach the BBC Microbit tracker to a battery back

Attach to a harness or collar, securing with a string

Plug the second BBC Microbit into the computer used

Ensure numbers displayed on both microbits align

###### Project Status

Complete

##### Room for Improvement

Visualisation for tracking movements

Potential for a GPS tracking


To do


## Acknowledgements


BBC. (2025, July 9). Introducing the BBC micro:bit - BBC Make It Digital. Youtube. https://youtu.be/Wuza5WXiMkc

Donat, W. (2017). Getting started with the micro:bit : coding and making with the BBC’s Open Development Board  (First edition.). Maker Media.

‌Halfacree, G. (2018). _The official BBC micro:bit user guide_ . John Wiley & Sons.

Instructables. (2021). Animal Tracker With Micro:bit. Instructables. https://www.instructables.com/Animal-Tracker-With-Microbit/
Micro:bit Educational Foundation. (2020). Animal tracker introduction. YouTube. https://www.youtube.com/watch?v=hEv0xds48Wo

Kuniavsky, M. (2008). User experience design for ubiquitous computing. _Interactions (New York, N.Y.)_, _15_(6), 20–22. https://doi.org/10.1145/1409040.1409045

Monk, S. (2019). _Micro:bit for mad scientists: 30 clever coding and electronics projects for kids_. No Starch Press, Inc

Pearce, M. (2016). Cat tracking program makes owners re-think pets’ behaviour and how they manage their moggies. Abc.net.au; ABC News. https://www.abc.net.au/news/2016-05-20/cat-tracking-program-makes-owners-re-think-pet-behaviour/7431248
‌
