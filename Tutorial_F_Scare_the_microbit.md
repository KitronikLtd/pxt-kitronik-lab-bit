### @activities true
### @explicitHints true

# Tutorial - Scare the micro:bit

## Introduction
### Introduction @unplugged
This tutorial will show how to detect sound levels with the microphone on the Kitronik LAB:bit.  
The tutorial will go through what an analog input is and how it can be used to create a fun mini game to scare the BBC micro:bit.

![microphone image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/microphone.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit with a micro USB (from the computer) connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  
When done, click ``||kitronik_lab_bit.Ok||`` to continue.

### What is an Analog input? @unplugged
Analog inputs are the type of inputs that vary with a smooth progression. Examples of these are sound, pedals on a bike etc.  
This smoothness in change can enable finer adjustment for the required application.
![microphone image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/microphone.png)

## Microphone Input
### Step 1
To begin with, we need to make a variable. The variable will be a named item to save the microphone reading to.  
Click on the ``||variables:Variables||`` section from the list of blocks, then click on **Make a Variable...**.  
This pops up a window to give your variable its name. Let's call it ``||variables:sound level||``.

### Step 2
Next, we want to use the ``||variables:set sound level||`` block and place it into the ``||basic:forever||`` loop.
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = 0
})
```

### Step 3
The ``||variables:set sound level||`` block needs to save the microphone reading.  
Place a ``||kitronik_lab_bit.measure sound volume||`` block into the end of the ``||variables:set sound level||``. The microphone input will give us a number from 0 to 100.
#### ~ tutorialhint
```blocks
let sound_level = 0
basic.forever(function () {
    sound_level = kitronik_lab_bit.readScaledSoundLevel()
})
```

### Step 4
We need to determine next whether the sound level is above a certain level. To do this decision making, there is a block called ``||logic:if else||``.  
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
``||logic:if||`` statements work like this: If something happens, use the blocks in the upper bracket, otherwise (else) use the blocks in the lower bracket.  
So, in the top bracket, we want the blocks for the micro:bit to react to the sound. In the top section of the ``||logic:if else||``, insert ``||basic:show icon||`` and select the surprised icon.  
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
To make sure the micro:bit stays surprised for a period of time, add a ``||basic:pause||`` after the ``||basic:show icon||`` and set it to 1 second (1000 milliseconds).
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
Now we need to have the code for when the micro:bit is not showing a surprised face.  
In the bottom section of the ``||logic:if else||``, insert ``||basic:show icon||`` and select the happy icon.  
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
Currently, we only have a ``||logic:true||`` condition in the ``||logic:if||`` statement. Our condition that needs to be checked is whether the sound level is greater than (a number).  
From the ``||logic:Logic||`` section, add a ``||logic:greater than||`` block and place it where the word **true** is in the ``||logic:if||`` block.  
**NOTE:** The greater than symbol looks like ``||logic:>||``.
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
To continue making the condition checking statement, add a ``||variables:sound level||`` block into the first position in the ``||logic:greater than||`` check.
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
The number we need to compare against might be different depending on the background sound level in the room you are in.  
To start with, set the check to be ``||variables:sound level||`` ``||logic:greater than||`` 50.  
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
Click ``|Download|`` to program the BBC micro:bit with the code. Test your code by making a loud sound.  
If you find your micro:bit does not scare easily, lower the number in the ``||logic:if||`` statement check (e.g. 40).  
If you find your micro:bit does scares very easily, raise the number in the ``||logic:if||`` statement check (e.g. 60).  
Once you have changed the number to suit your micro:bit, click ``|Download|`` and test your code again.

### Scare the micro:bit tutorial complete @unplugged
All that loud noise is making me scared. We've done a great job looking at analog sound inputs and if statements.  
It's not just the micro:bit display you could use to react to sound, you could try the motor or the ZIP LEDs.  
This tutorial has been completed, however, there are still loads of project that could be created.  
If you wish to know more about the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
