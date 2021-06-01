### @activities true
### @explicitHints true

# Tutorial - Scare the micro:bit

## Introduction
### Introduction @unplugged
The tutorial will show how to detect sound levels with the microphone on the Kitronik LAB:bit.  The tutorial will go through what an analog input is, how is can be used to create a fun mini game to scare the BBC micro:bit.

![microphone image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/microphone.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit and with a micro USB (from the computer) is connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  When done click next to continue.

### What is an Analog input? @unplugged
Analog inputs are the type of inputs that vary in change with a smooth progression. Examples of these are sound, pedals on a bike. This smoothness in change can give a fine tune to what is required.
![microphone image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/microphone.png)

## Speed control
### Step 1
To begin with we need to make a variable. The variable will be a named item that save the microphone reading to.  
Click on the "variables" section from the list of block, then click on "Make a Variable".  This pop up a window to give your variable its need.  Lets call it "sound level".

### Step 2
Next we want to use the ``||variables:set sound level||`` place it into the ``||basic:forever loop||``.
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = 0
})
```

### Step 3
The ``||variables:set sound level||`` needs to save the microphone reading. Place a ``||kitronik_lab_bit.measure sound volume||`` block into the end of the ``||variables:set sound level||``.  
The microphone input will give us a number from 0 to 100
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = kitronik_lab_bit.readScaledSoundLevel()
})
```

### Step 4
We need to determine next if the sound level is above a certain level.  To do this desicion making there is a block call ``||logic:if else||``.  
From the list of blocks, insert an ``||logic:if else||`` block after the ``||variables:set sound level||``.
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = kitronik_lab_bit.readScaledSoundLevel()
    if (true) {

    } else {

    }
})
```

### Step 5
If blocks like this. If something happens, use the blocks in the upper bracket, else use the blocks in the lower bracket.  
So in the top bracket we want the blocks for the micro:bit to react to the sound. In the top backet of the ``||logic:if else||`` insert ``||basic:show Icon||`` and select the surprised icon.  
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = kitronik_lab_bit.readScaledSoundLevel()
    if (true) {
        basic.showIcon(IconNames.Surprised)
    } else {

    }
})
```

### Step 6
To make sure the micro:bit stays surprised for a period of time, add a ``||basic:pause||`` after the ``||basic:show Icon||`` and set it to 1 seconds (1000 milliseconds)
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = kitronik_lab_bit.readScaledSoundLevel()
    if (true) {
        basic.showIcon(IconNames.Surprised)
        basic.pause(1000)
    } else {

    }
})
```

### Step 7
Now we need to have the block when the micro:bit is not showing a surprised face. 
In the top backet of the ``||logic:if else||`` insert ``||basic:show Icon||`` and select the happy icon.  
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = kitronik_lab_bit.readScaledSoundLevel()
    if (true) {
        basic.showIcon(IconNames.Surprised)
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

### Step 8
Currently we only have a "true" condition in the if statement.  Our condition that needs to check if the sound level is greater than (a number).
Add from the logic section a ``||logic:greater than||`` block and place it where the word "true" is in the ``||logic:if||`` block.  
NOTE: the greater than symbol looks like '>'
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = kitronik_lab_bit.readScaledSoundLevel()
    if (0 > 0) {
        basic.showIcon(IconNames.Surprised)
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

### Step 9
Following on from the "if the sound level is greater than (a number)". Add a ``||variables:sound level||`` into the first position of the left '0' of the ``||logic:greater than||`` block.
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = kitronik_lab_bit.readScaledSoundLevel()
    if (sound_level > 0) {
        basic.showIcon(IconNames.Surprised)
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

### Step 10
The number we need to compare against maybe different depending on the background sound level in the room you are in.  
To start with let begining with setting the ``||variables:sound level||`` ``||logic:greater than||`` 50.  
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = kitronik_lab_bit.readScaledSoundLevel()
    if (sound_level > 50) {
        basic.showIcon(IconNames.Surprised)
        basic.pause(1000)
    } else {
        basic.showIcon(IconNames.Happy)
    }
})
```

### Step 11
Click ``|Download|`` to program the BBC micro:bit with the code. Test your code my making a loud sound.  
If you find your micro:bit does not scare easily, lower the number in the if statement for example 40.  
If you find your micro:bit does scares very easily, raise the number in the if statement for example 60.  
Once you have changed the number to suit your micro:bit click ``|Download|`` and test your code.

### Scare the micro:bit tutorial complete @unplugged
All that loud noise is making me scared. So we done a great job looking at analog sound inputs and if statements.  
Its not just the micro:bit display you could use to react to sound, you could try the motor or the ZIP LED's.  
This tutorial has been completed, however there are still loads of project that could be created.  
If you wish to know more on the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
