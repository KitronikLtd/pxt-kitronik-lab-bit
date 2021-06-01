### @activities true
### @explicitHints true

# Tutorial - Traffic light sequnce

## Introduction
### Introduction @unplugged
Learn how to control the Traffic Light sequence on the Kitronik LAB:bit.  The tutorial will go through how to control the traffic light LED's and the sequence/algorithm that are used.

![trafficLight image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/trafficLight.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit and with a micro USB (from the computer) is connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  When done click next to continue.

### What is an LED? @unplugged
LED stands for Light Emitting Diode.  This is a type of electronic component and when electrical current flows in a particular direction it will make the LED light up.
The software blocks can be used to help control whether the electrical current flows or not thus resulting in the LED turning on or off.  
LED's can come in many differnt shapes and sizes.
![LED image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/led.png)

## Control the Traffic Lights
### Step 1
There is just one block that is used for the traffic light control.  From this block can change the which lights are on or off and which set of traffic lights on the LAB:bit is being controlled.  
First insert a ``||kitronik_lab_bit.traffic light||`` block into the ``||basic:forever||`` bracket. Click on each of the colour icons will bring up a colour selection, the lighter colour idicates the LED is on, the darker colour indicates the LED is off.  
Lets set only the Red LED to be turned on.
#### ~ tutorialhint
```blocks
basic.forever(function () {
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0x878604,
    0x0f4604
    )
})
```
### Step 2
Click ``|Download|`` to program the BBC micro:bit with the code. A Red LED on traffic light 1 will turn on.

### What is an algorithm? @unplugged
Algorithms are a step-by-step guide for code and/or computer to completing a task. The algorithm for a set of trafficlights would be the order the lights change.  
It is possible to have algorithm for making a sandwich.  So long that the algorithm produces the end point require it does not matter which order the steps are take to complete it.
![step image](https://KitronikLtd.github.io/pxt-kitronik-labbit/assets/step.png)

### What is the algorithm for traffic lights? @unplugged
See if you can write done the algorithms (step-by-step process) for the light sequence.  This will come in handy when we try and code the algorithm.
![trafficLight image](https://KitronikLtd.github.io/pxt-kitronik-labbit/assets/trafficLight.png)

### Step 3
Now we have our algorithm, lets start coding. There is 4 main stages of which lights are shown on a traffic light.  We can do the next one together.  
Add another ``||kitronik_lab_bit.traffic light||`` and from the colour pallets turn on the Red and Yellow LED'seconds
#### ~ tutorialhint
```blocks
basic.forever(function () {
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0x878604,
    0x0f4604
    )
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0xffff00,
    0x0f4604
    )
})
```

### Step 4
See if you can add the next two ``||kitronik_lab_bit.traffic light||`` blocks to create the full traffic algorithm.
#### ~ tutorialhint
```blocks
basic.forever(function () {
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0x878604,
    0x0f4604
    )
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0xffff00,
    0x0f4604
    )
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0x900606,
    0x878604,
    0x00ff00
    )
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0x900606,
    0xffff00,
    0x0f4604
    )
})
```

### Step 5
Click ``|Download|`` to program the BBC micro:bit with the code. See if its correct or if something strange happens.

### Step 6
There seems to be any issue with the sequence. Computer algorithm can process instructions very quickly, so quick that the LED dont appear to be changing.
This can be fixed by adding a ``||basic:pause||`` inbetween each of the ``||kitronik_lab_bit.traffic light||`` blocks.
#### ~ tutorialhint
```blocks
basic.forever(function () {
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0x878604,
    0x0f4604
    )
    basic.pause(100)
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0xffff00,
    0x0f4604
    )
    basic.pause(100)
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0x900606,
    0x878604,
    0x00ff00
    )
    basic.pause(100)
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0x900606,
    0xffff00,
    0x0f4604
    )
    basic.pause(100)
})
```

### Step 7
Before we download the code, have a look at each of the timings. A real life traffic light does not stay on the same stage for the same length of time.  
For example red light only and green ligths only are much longer wait than the other.  Set the time of the first and third pause to 1 second (1000 milliseconds).  
The second and forth will be set to 0.2 seconds (200 milliseconds)
#### ~ tutorialhint
```blocks
basic.forever(function () {
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0x878604,
    0x0f4604
    )
    basic.pause(1000)
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0xffff00,
    0x0f4604
    )
    basic.pause(200)
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0x900606,
    0x878604,
    0x00ff00
    )
    basic.pause(1000)
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0x900606,
    0xffff00,
    0x0f4604
    )
    basic.pause(200)
})
```

### Step 8
Click ``|Download|`` lets have a look at the sequence now.

### Traffic Light tutorial complete @unplugged
WOW, you have done great, we manage to make an alogrythm and code it.  See if you can add a second sequence on to the second set of traffic lights and have both changing.  This could be made into a crossing.  
This tutorial has been completed, however there are still loads of project that could be created.  
If you wish to know more on the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
