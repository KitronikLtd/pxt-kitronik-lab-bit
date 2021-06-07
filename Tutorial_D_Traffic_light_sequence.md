### @activities true
### @explicitHints true

# Tutorial - Traffic Light Sequence

## Introduction
### Introduction @unplugged
Learn how to control the Traffic Light sequence on the Kitronik LAB:bit.  
The tutorial will go through how to control the traffic light LEDs and the sequence/algorithm that is used.

![trafficLight image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/trafficLight.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit with a micro USB (from the computer) connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  
When done, click ``||kitronik_lab_bit.Ok||`` to continue.

### What is an LED? @unplugged
LED stands for Light Emitting Diode.  This is a type of electronic component and when electrical current flows in a particular direction it will make the LED light up.
The software blocks can be used to help control whether the electrical current flows or not, resulting in the LED turning on or off.  
LEDs can come in many different shapes and sizes.
![LED image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/led.png)

## Control the Traffic Lights
### Step 1
There is just one block that is used for the traffic light control.  
From this block, you can change which lights are on or off, and which set of traffic lights on the LAB:bit are being controlled.  
First, insert a ``||kitronik_lab_bit.traffic light||`` block into the ``||basic:forever||`` bracket. Clicking on each of the colour icons will bring up a colour selection.  
The lighter colour indicates the LED is **on**, the darker colour indicates the LED is **off**.  
Let's set only the Red LED to be turned on.
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
Click ``|Download|`` to program the BBC micro:bit with the code. The Red LED on traffic light 1 will turn on.

### What is an algorithm? @unplugged
Algorithms are a step-by-step guide for code and/or a computer to completie a task.  
The algorithm for a set of traffic lights would be the order the lights change.  
It is possible to have an algorithm for making a sandwich. As long as the algorithm produces the end point required, it does not matter which order the steps are taken to complete it.
![step image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/step.png)

### What is the algorithm for traffic lights? @unplugged
See if you can write down the algorithm (step-by-step process) for the light sequence. This will come in handy when we try and code it next.
![trafficLight image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/trafficLight.png)

### Step 3
Now we have our algorithm, let's start coding. There are 4 main stages to the light patterns which are shown on a traffic light. We can do the next one together.  
Add another ``||kitronik_lab_bit.traffic light||`` block, and from the colour palette turn on the Red and Yellow LEDs.
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
See if you can add the next two ``||kitronik_lab_bit.traffic light||`` blocks to create the full traffic light algorithm.
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
Click ``|Download|`` to program the BBC micro:bit with the code. See if it's correct or whether something strange happens...

### Step 6
There seems to be any issue with the sequence. Computer algorithms can process instructions very quickly, so quickly in fact, that the LEDs don't appear to be changing.  
This can be fixed by adding a ``||basic:pause||`` after each of the ``||kitronik_lab_bit.traffic light||`` blocks.
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
For example, red light only and green light only are much a longer wait than the others. Set the time of the first and third pause to 1 second (1000 milliseconds).  
The second and fourth should be set to 0.5 seconds (500 milliseconds).
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
    basic.pause(500)
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
    basic.pause(500)
})
```

### Step 8
Click ``|Download|`` and have a look at the sequence now.

### Traffic Light tutorial complete @unplugged
WOW, you have done great! We managed to make an alogrithm and code it. See if you can add a second sequence on to the other set of traffic lights and have both changing. This could be made into a crossing.  
This tutorial has been completed, however, there are still loads of project that could be created.  
If you wish to know more about the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
