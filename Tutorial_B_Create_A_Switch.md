### @activities true
### @explicitHints true

# Tutorial - Create a switch

## Introduction
### Introduction @unplugged
Learn how to create a home made switch and use it with the Kitronik LAB:bit.  The tutorial will go through what are switches and how they are used.  
Creating a simple code to show when the switch is working. Followed by testing different materials.

![switch image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/switch.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit and with a micro USB (from the computer) is connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  When done click next to continue.

### What is a switch? @unplugged
A switch is another word for a button. Buttons and switches are used in lots of different products. For example: TV remotes, doorbells, light switches etc.  
Switches are used to indicate to computers that an activity needs to happen. Typically with two positions such as 'On' or 'Off'.  
Have a think of any other products around that have a buttons or switches.  How many can you name?  
The code that will be create will have a basic activity happen once a switch/ button has been pressed the BBC micro:bit LEDs/lights will turn On.  
![switch image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/switch.png)

## Activate the switch
### Step 1
Lets start by bring in the ``||input:on Button Pressed||`` bracket into the editing space.
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {

})
```

### Step 2
The basic activity will be to display an image on the BBC micro:bit screen.  Inside of the ``||input:on Button Pressed||`` bracket place a  ``||basic:show Icon||``.  
Once complete, click ``|Download|`` and this will program the BBC micro:bit with the code we have just created.
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Happy)
})
```

### Smiling BBC micro:bit @unplugged
The code is working so far, thats great!. Did you notice the smiling face is still on the screen and not gone? How will we know when the switch is next activated?.  
We can add some extra two blocks to change this.  Click next to progress to the next stage.

### Step 3
Before the screen is cleared we need to wait (or pause) for a period of time for the image to be shown on the BBC micro:bit display.  
Add a ``||basic:pause||`` block below the ``||basic:show Icon||`` and set it to 1 second (or 1000 milliseonds)
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Happy)
    basic.pause(1000)
})
```

### Step 4 
Add a ``||basic:clear screen||`` at the bottom to turn off the display LED's
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    basic.showIcon(IconNames.Happy)
    basic.pause(1000)
    basic.clearScreen()
})
```

### Step 5
Click ``|Download|`` to program the BBC micro:bit with the code. See if the display clears after the button has been pressed.

### Try different materials @unplugged
Different material will either conduct electricity or not (also known as insolators).  
Try a range of items (such as paper, tin foil, plasitcs, cans etc) and connect across the two switch input pads and see if they make a connection and activate the switch.  
If the switch activates then the material is a conductive material.

### Create a switch tutorial complete @unplugged
Well done, you have succeeded in creating a switch input. This tutorial has been completed, however there are still loads of project that could be created.  
If you wish to know more on the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
