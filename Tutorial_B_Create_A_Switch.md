### @activities true
### @explicitHints true

# Tutorial - Create a Switch

## Introduction
### Introduction @unplugged
Learn how to create a homemade switch and use it with the Kitronik LAB:bit.  
The tutorial will go through what are switches and how they are used, creating a simple program to show when the switch is working.  
This will be followed by testing different materials.

![switch image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/switch.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit with a micro USB (from the computer) connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  
When done, click ``||kitronik_lab_bit.Ok||`` to continue.

### What is a switch? @unplugged
A switch is another word for a button. Buttons and switches are used in lots of different products. For example: TV remotes, doorbells, light switches etc.  
Switches are used to indicate to computers that an activity needs to happen, typically with two positions, such as 'On' or 'Off'.  
Have a think of any other products that have buttons or switches. How many can you name?  
The code that will be create will have a basic activity happen once a switch/button has been pressed.  

![switch image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/switch.png)

## Activate the switch
### Step 1
Let's start by bringing in the ``||input:on Button Pressed||`` bracket into the editing space.
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {

})
```

### Step 2
The basic activity will be to display an image on the BBC micro:bit screen.  Inside of the ``||input:on Button Pressed||`` bracket place a  ``||basic:show Icon||`` block.  
Once complete, click ``|Download|`` and this will program the BBC micro:bit with the code we have just created.
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Happy)
})
```

### Smiling BBC micro:bit @unplugged
The code is working so far, that's great! Did you notice the smiling face is still on the screen and not gone? How will we know when the switch is next activated?  
We can add an extra two blocks to change this. Click ``||kitronik_lab_bit.Ok||`` to progress to the next stage.

### Step 3
Before the screen is cleared we need to wait (or pause) for a period of time for the image to be shown on the BBC micro:bit display.  
Add a ``||basic:pause||`` block below the ``||basic:show icon||`` and set it to 1 second (or 1000 milliseonds)
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Happy)
    basic.pause(1000)
})
```

### Step 4 
Add a ``||basic:clear screen||`` at the bottom to turn off the display LEDs.
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Happy)
    basic.pause(1000)
    basic.clearScreen()
})
```

### Step 5
Click ``|Download|`` to program the BBC micro:bit with the code. Check that the display clears after the button has been pressed.

### Try different materials @unplugged
Different material will either conduct electricity or not (also known as isolators).  
Try a range of items (such as paper, tin foil, plastics, cans etc) and connect across the two 'A Switch Input' pads and see if they make a connection and activate the switch.  
If the switch activates then the material is a conductive material.

### Create a switch tutorial complete @unplugged
Well done, you have succeeded in creating a switch input.  
This tutorial has been completed, however there are still loads of project that could be created.  
If you wish to know more about the Kitronik LAB:bit visit: 
http://www.kitronik.co.uk/56101
