### @activities true
### @explicitHints true

# Tutorial - Make a Dice

## Introduction
### Introduction @unplugged
Learn how to create a digital dice on the Kitronik LAB:bit.  
The tutorial will go through what LEDs are and how to control them, and then different ways of activating the dice to give us a number.

![Dice image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/dice.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit with a micro USB (from the computer) connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  
When done, click ``||kitronik_lab_bit.Ok||`` to continue.

### What is an LED? @unplugged
LED stands for Light Emitting Diode.  This is a type of electronic component and when electrical current flows in a particular direction it will make the LED light up.
The software blocks can be used to help control whether the electrical current flows or not, resulting in the LED turning on or off.  
LEDs can come in many different shapes and sizes.

![LED image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/led.png)

## Showing numbers and text on the screen
### Step 1
To begin with, we will display a dice pattern on the LEDs. From the LAB:bit list of blocks you can click and drag the required blocks into the editor.  
Find the ``||kitronik_lab_bit.roll on dice||`` and place it into the ``||basic:on start||`` bracket.  
Once complete, you can choose any number between 1 and 6 within this block to be shown on the dice.
#### ~ tutorialhint
```blocks
kitronik_lab_bit.diceShow(1)
```

### Step 2
Make sure your BBC micro:bit is connected to your computer via a micro USB cable.  
Click ``|Download|`` and this will program the BBC micro:bit with the code we have just created. Check out the dice to see your number appear.  
If you wish to change the number to see a different pattern, simply change the number in the block and click ``|Download|`` again.

### Step 3
Now we have the output working, let's apply an input to activate this block.  
Start by adding an ``||input:on Button Pressed||`` block and move the ``||kitronik_lab_bit.roll on dice||`` into this new block.
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    kitronik_lab_bit.diceShow(1)
})
```

### Step 4
Click ``|Download|`` and this will program the BBC micro:bit with the code we have just created. Now the dice will appear once the button has been pressed.

### Step 5
So far so good! However, we have only been showing one number on the dice LEDs - that's not much of a dice.  
In the Math section there is a ``||math:random||`` block. Add this into the ``||kitronik_lab_bit.roll on dice||``.  
See if you can add the range of numbers that appear on a normal dice.
#### ~ tutorialhint
```blocks
input.onButtonPressed(Button.A, function () {
    kitronik_lab_bit.diceShow(randint(1, 6))
})
```

### Step 6
Let's ``|Download|`` the code to the BBC micro:bit and see what happens if the button is pressed over and over again.

### Step 7
Great, it's changing every time now. Did you know the BBC micro:bit has an input that responds when you shake it?  
Let's add the ``||input:shake||`` input and move the ``||kitronik_lab_bit.roll on dice||`` into this bracket (keep the ``||math.random||`` block inside as well).  
Now this means to change the dice you have to shake the LAB:bit.
#### ~ tutorialhint
```blocks
input.onGesture(Gesture.Shake, function () {
    kitronik_lab_bit.diceShow(randint(1, 6))
})
```

### Step 8
Finally the last stage, click ``|Download|`` and try shaking the LAB:bit.

### Make a Dice tutorial complete @unplugged
Well done, you have succeeded in creating an electronic dice in code.  
This tutorial has been completed, however there are still loads of project that could be created.  
If you wish to know more about the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
