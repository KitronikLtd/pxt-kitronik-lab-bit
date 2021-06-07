### @activities true
### @explicitHints true

# Tutorial - Speed Control

## Introduction
### Introduction @unplugged
Learn how to use an analog input and then use it to control the speed of a motor on the Kitronik LAB:bit.  
The tutorial will go through what an analog input is and how is can be used to control a motor.

![analog image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/metre.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit with a micro USB (from the computer) connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  
When done, click ``||kitronik_lab_bit.Ok||`` to continue.

### What is an Analog input? @unplugged
Analog inputs are the type of inputs that vary with a smooth progression. Examples of these are sound, pedals on a bike etc.  
This smoothness in change can enable finer adjustment for the required application.
![analog image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/analog.png)

## Speed control
### Step 1
To begin with, we need to make a variable. The variable will be a named item that we can save the analog reading to.  
Click on the ``||variables:Variables||`` section from the list of blocks, then click on **Make a Variable...**.  
This pops up a window to give your variable its name. Let's call it ``||variables:speed||``.

### Step 2
Next we want to use the ``||variables:set speed||`` block and place it into the ``||basic:forever||`` loop.
#### ~ tutorialhint
```blocks
basic.forever(function () {
    speed = 0
})
```

### Step 3
The ``||variables:set speed||`` block needs to save the analog reading. Place a ``||kitronik_lab_bit.read analog input||`` block into the end of ``||variables:set speed||``.  
The analog input will give us a number from 0 to 100.
#### ~ tutorialhint
```blocks
basic.forever(function () {
    speed = kitronik_lab_bit.readAnalogInput()
})
```

### Step 4
Now we have our readings saved, next, the motor needs respond to the input.  
Add a ``||kitronik_lab_bit.turn motor||`` block underneath the ``||variables:set speed||`` block.
#### ~ tutorialhint
```blocks
basic.forever(function () {
    speed = kitronik_lab_bit.readAnalogInput()
    kitronik_lab_bit.motorOn(kitronik_lab_bit.MotorDirection.CW, 0)
})
```

### Step 5
You may have noticed the new motor block has speed set to 0, meaning the motor won't move. The speed of the motor works on a number between 0 and 100.  
The analog input gives us the same range, so we can add ``||variables:speed||`` into the ``||kitronik_lab_bit.turn motor||`` block.
#### ~ tutorialhint
```blocks
basic.forever(function () {
    speed = kitronik_lab_bit.readAnalogInput()
    kitronik_lab_bit.motorOn(kitronik_lab_bit.MotorDirection.CW, speed)
})
```

### Step 6
Click ``|Download|`` to program the BBC micro:bit with the code. Once complete, alter the analog input on the LAB:bit and see how the motor responds.

### Speed control tutorial complete @unplugged
Awesome, we have fine adjustment and control of the motor from an anlog input. In the kit there is a yellow wheel (if you have not seen it already) - you can place it on the motor for use with any other projects.  
This tutorial has been completed, however, there are still loads of project that could be created.  
If you wish to know more about the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
