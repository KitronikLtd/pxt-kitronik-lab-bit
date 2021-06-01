### @activities true
### @explicitHints true

# Tutorial - Parking sensor

## Introduction
### Introduction @unplugged
The tutorial will demonstrate the use of the ultrasonic sensor on the Kitronik LAB:bit.  The tutorial will go through how an ultrasonic sensor works, and create a parking sensor.

![car image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/car.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit and with a micro USB (from the computer) is connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  When done click next to continue.

### How does an ultrasonic sensor work? @unplugged
Ultrasonic sensors work by having one part of the device send out a high pitch noise (so high humans cant hear it), then the second half of the sensors measures to returning echo when it bounces from an object.  
This is another version of echolocation that Bats use to find objects in the night and Dolphins have to find things in the oceans.
![dolphin image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/dolphin.png)

## Measure the distance
### Step 1
To begin with we need to make a variable. The variable will be a named item that save the measuring reading from the ultrasonic.  
Click on the "variables" section from the list of block, then click on "Make a Variable".  This pop up a window to give your variable its need.  Lets call it "distance".

### Step 2
Next we want to use the ``||variables:set distance||`` place it into the ``||basic:forever loop||``.
#### ~ tutorialhint
```blocks
let distance = 0
basic.forever(function () {
    distance = 0
})
```

### Step 3
The ``||variables:set distance||`` needs to save the ultrasonic measurement reading. Place a ``||kitronik_lab_bit.measure distance in cm||`` into the end of the ``||variables:set distance||``.  
The reading from the ultrasonic will be in centimeters in this example, but if you want to measure in inches just use the ``||kitronik_lab_bit.measure distance in inches||`` block
#### ~ tutorialhint
```blocks
let distance = 0
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
})
```

### Step 4
We need to determine next if the distance to an object is close enough to start the beeps to alert someone.  To do this desicion making there is a block call ``||logic:if||``.  
From the list of blocks, insert an ``||logic:if||`` block after the ``||variables:set distance||``.
#### ~ tutorialhint
```blocks
let distance = 0
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
    if (true) {

    } 
})
```

### Step 5
If blocks like this. If something happens, use the blocks in the bracket.  
So in the bracket we want the blocks for the micro:bit to react to the sound. In the backet of the ``||logic:if||`` insert ``||music:playTone||`` and select 1/8 beat.  
#### ~ tutorialhint
```blocks
let distance = 0
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
    if (true) {
        music.playTone(262, music.beat(BeatFraction.Eighth))
    } 
})
```

### Step 6
Next we will add in a ``||basic:pause||`` to allow a gap between each tone being sounded. Later on we will add a cool feature to this block.
#### ~ tutorialhint
```blocks
let distance = 0
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
    if (true) {
        music.playTone(262, music.beat(BeatFraction.Eighth))
        basic.pause(100)
    } 
})
```

### Step 7
Currently we only have a "true" condition in the if statement.  Our condition that needs to check if the distance is less than (a number).
Add from the logic section a ``||logic:less than||`` block and place it where the word "true" is in the ``||logic:if||`` block.  
NOTE: the less than symbol looks like '<'
#### ~ tutorialhint
```blocks
let distance = 0
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
    if (0 < 0) {
        music.playTone(262, music.beat(BeatFraction.Eighth))
        basic.pause(100)
    } 
})
```

### Step 8
Looking back at our condition "if the distance is less than (a number)". Add a ``||variables:distance||`` into the first position of the left '0' of the ``||logic:less than||`` block.
#### ~ tutorialhint
```blocks
let distance = 0
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
    if (distance < 0) {
        music.playTone(262, music.beat(BeatFraction.Eighth))
        basic.pause(100)
    } 
})
```

### Step 9
The number we need to compare against maybe different depending on what opbjects are around you.  
Make sure you have atleast 20 centimeters clearance from the ultrasonic sensors on the LAB:bit.    
To start with let begining with setting the ``||variables:distance||`` ``||logic:less than||`` 20.  
#### ~ tutorialhint
```blocks
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
    if (distance < 20) {
        music.playTone(262, music.beat(BeatFraction.Eighth))
        basic.pause(100)
    }
})
```

### Step 11
Click ``|Download|`` to program the BBC micro:bit with the code. Test your code my placing any obeject within 20 centimeters of the sensor and the LAB:bit should beep when its detected it.  
NOTE: Check the volumne control on the speaker if no sound is being made.

### Step 12
We got our basic detection working.  Now lets add a cool feature, this will change the pause time depending on the distance measured.  In the ``||basic:pause||`` add ``||math:times||`` block.  
#### ~ tutorialhint
```blocks
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
    if (distance < 20) {
        music.playTone(262, music.beat(BeatFraction.Eighth))
        basic.pause(0 * 0)
    }
})
```

### Step 13
The distance measure will form part of the pause equation.  Add ``||variables:distance||`` into the left part of the ``||math:times||`` block.
#### ~ tutorialhint
```blocks
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
    if (distance < 20) {
        music.playTone(262, music.beat(BeatFraction.Eighth))
        basic.pause(distance * 0)
    }
})
```

### Step 14
The distance work on 1 to 20, however the pause block works in milliseconds.  So we need to increase our distance reading to make for a good pause length.  In this example we will use 50.
#### ~ tutorialhint
```blocks
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
    if (distance < 20) {
        music.playTone(262, music.beat(BeatFraction.Eighth))
        basic.pause(distance * 50)
    }
})
```

### Step 15
Lets ``|Download|`` to program the BBC micro:bit. Test your code  and see if the time between each 'beep' changes when an objects gets closer.
NOTE: Check the volumne control on the speaker if no sound is being made.

### Parking sensor tutorial complete @unplugged
Great job on creating a parking sensor. You can take the LAB:bit and make sure you dont bump into any object.  
This tutorial has been completed, however there are still loads of project that could be created.  
If you wish to know more on the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
