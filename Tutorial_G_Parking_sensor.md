### @activities true
### @explicitHints true

# Tutorial - Parking Sensor

## Introduction
### Introduction @unplugged
This tutorial will demonstrate the use of the ultrasonic sensor on the Kitronik LAB:bit.  
The tutorial will go through how an ultrasonic sensor works and creating a parking sensor.

![car image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/car.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit with a micro USB (from the computer) connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  
When done, click ``||kitronik_lab_bit.Ok||`` to continue.

### How does an ultrasonic sensor work? @unplugged
Ultrasonic sensors work by having one part of the device send out a high pitch noise (so high that humans can't hear it), then the second half of the sensor measures the returning echo when it bounces off an object.  
This is another version of echolocation that bats use to find objects in the night and dolphins use to find things in the oceans.
![dolphin image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/dolphin.png)

## Measure the distance
### Step 1
To begin with, we need to make a variable. The variable will be a named item that saves the reading from the ultrasonic sensor.  
Click on the ``||variables:Variables||`` section from the list of blocks, then click on **Make a Variable...**.  
This pops up a window to give your variable its name. Let's call it ``||variables:distance||``.

### Step 2
Next, we want to use the ``||variables:set distance||`` and place it into the ``||basic:forever||`` loop.
#### ~ tutorialhint
```blocks
let distance = 0
basic.forever(function () {
    distance = 0
})
```

### Step 3
The ``||variables:set distance||`` block needs to save the ultrasonic measurement reading. Place a ``||kitronik_lab_bit.measure distance in cm||`` block into the end of the ``||variables:set distance||``.  
The reading from the ultrasonic will be in centimeters in this example, but if you want to measure in inches just use the ``||kitronik_lab_bit.measure distance in inches||`` block
#### ~ tutorialhint
```blocks
let distance = 0
basic.forever(function () {
    distance = kitronik_lab_bit.measureCm()
})
```

### Step 4
We need to determine next if the distance to an object is close enough to start the beeps to alert someone.  
To do this desicion making, there is a block call ``||logic:if||``. From the list of blocks, insert an ``||logic:if||`` block after the ``||variables:set distance||``.
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
``||logic:if||`` statements work like this: If something happens, use the blocks in the bracket.  
So, in the bracket, we want the blocks for the micro:bit to react to the sound.  
Insert ``||music:playTone||`` into the bracket and select 1/8 beat.  
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
Next, we will add in a ``||basic:pause||`` to allow a gap between each tone being sounded. Later on we will add another cool feature to this block...
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
Currently, we only have a ``||logic:true||`` condition in the ``||logic:if||`` statement. Our condition that needs to be checked is whether the distance is less than (a number).
From the ``||logic:Logic||`` section, add a ``||logic:less than||`` block and place it where the word **true** is in the ``||logic:if||`` block.  
**NOTE:** The less than symbol looks like ``||logic:<||``.
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
To continue making the condition checking statement, add a ``||variables:distance||`` block into the first position in the ``||logic:less than||`` check.
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
The number we need to compare against might be different depending on what objects are around you.  
Make sure you have at least 20cm clearance from the ultrasonic sensors on the LAB:bit.  
To start with, set the check to ``||variables:distance||`` ``||logic:less than||`` 20.  
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
Click ``|Download|`` to program the BBC micro:bit with the code.  
Test your code my placing any object within 20cm of the sensor and the LAB:bit should beep when it's detected it.  
**NOTE:** Check the volumne control on the speaker if no sound is being made.

### Step 12
We got our basic detection working. Now let's add a cool feature which will change the pause time depending on the distance measured.  
In the ``||basic:pause||``, add a ``||math:times||`` block.  
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
The distance measurement will form part of the pause equation. Add ``||variables:distance||`` into the left part of the ``||math:times||`` block.
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
The distance works from 1 to 20, but the ``||basic:pause||`` block works in milliseconds.  
We need to increase our distance reading to make sure there is a good pause length. In this example, we will multiply by 50.
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
Let's ``|Download|`` the program the BBC micro:bit. Test your code and see if the time between each 'beep' changes when an object gets closer.  
**NOTE:** Check the volumne control on the speaker if no sound is being made.

### Parking sensor tutorial complete @unplugged
Great job on creating a parking sensor. You can take the LAB:bit and make sure you don't bump into anything.  
This tutorial has been completed, however, there are still loads of project that could be created.  
If you wish to know more about the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
