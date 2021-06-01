### @activities true
### @explicitHints true

# Tutorial - Colour a rainbow

## Introduction
### Introduction @unplugged
Learn how to use the ZIP LED's with the Kitronik LAB:bit.  The tutorial will go through how to set the ZIP's up, how to pick the coluors and other features.

![rainbow image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/rainbow.png)

### Setup and connections of the LAB:bit @unplugged
Make sure that the BBC micro:bit is plugged into the LAB:bit and with a micro USB (from the computer) is connected to the BBC micro:bit.  
Add the power supply to the LAB:bit with either the 3xAA battery cage or the USB lead to a mains adapter.  When done click next to continue.

### What is the ZIP LEDs? @unplugged
The ZIP LED's are programmable type of LED.  Each one has 3 main colours inside, Red, Green and Blue.  
Depending on much each of these colours of turned on will show different colours and can give a full spectrum of colours from just one LED.  
The blocks for the LAB:bit take care of that control with a simple interface of just selecting which colour you want.  
![rainbow image](https://KitronikLtd.github.io/pxt-kitronik-lab-bit/assets/rainbow.png)

## Setup the ZIP LED's
### Step 1
Before any control of the ZIP LED's can be used a ``||kitronik_lab_bit.set pretty Lights||`` block and this is placed in the ``||basic:onstart||`` bracket.
#### ~ tutorialhint
```blocks
let prettyLights = kitronik_lab_bit.createZIPString(7)
```
### Setup complete @unplugged
Now that block is in the code, the ZIP LED's will be abe to be controlled from the software created. The LAB:bit has seven ZIP LED's on, and there are 7 different colours in the colour spectrum.  
The code we create will assign one ZIP LED with a single colour of the spectrum.  
You might like to research into all the colours of the spectrum before continuing the tutorial.  

### Step 2
Still adding blocks into the ``||basic:on start||`` bracket, lets set the first LED to Red colour.  This can be done by adding the ``||kitronik_lab_bit.set Zip Led Color||`` block to the bottom of the bracket.  
From the colour icon at the end of the block, click on this to pull up the colour pallet for the LED. Then click on the require colour.
NOTE: You may notice that the block has a 0 instead of a 1.  In the coding world 0 is always the first number to use.  So for the 7 LED's they will be address 0 to 6
#### ~ tutorialhint
```blocks
let prettyLights = kitronik_lab_bit.createZIPString(7)
prettyLights.setZipLedColor(0, 0xff0000)
```

### Step 3
Great, lets add another of the ``||kitronik_lab_bit.set Zip Led Color||``.  This is for the second LED, change the '0' to a '1'.  From the colour pallet, select Orange.
#### ~ tutorialhint
```blocks
let prettyLights = kitronik_lab_bit.createZIPString(7)
prettyLights.setZipLedColor(0, 0xff0000)
prettyLights.setZipLedColor(1, 0xff7700)
```

### Step 4
Well done, now to complete the the next part will need 5 more of the ``||kitronik_lab_bit.set Zip Led Color||``.  
See if you can add the blocks in, increase the number by 1 and select the next colour from the colour spectrum.  
There is also the tutorial hints if you get stuck
#### ~ tutorialhint
```blocks
let prettyLights = kitronik_lab_bit.createZIPString(7)
prettyLights.setZipLedColor(0, 0xff0000)
prettyLights.setZipLedColor(1, 0xff7700)
prettyLights.setZipLedColor(2, 0xd4ff00)
prettyLights.setZipLedColor(3, 0x5eff00)
prettyLights.setZipLedColor(4, 0x00bbff)
prettyLights.setZipLedColor(5, 0x9900ff)
prettyLights.setZipLedColor(6, 0xff3399)
```

### Step 5 
We now have all the colours set to different ZIP LED's, the next block that need to be added after any changes have been done is ``||kitronik_lab_bit.show changes||``.  
This block will make any changes to the ZIP LED's view able.
#### ~ tutorialhint
```blocks
let prettyLights = kitronik_lab_bit.createZIPString(7)
prettyLights.setZipLedColor(0, 0xff0000)
prettyLights.setZipLedColor(1, 0xff7700)
prettyLights.setZipLedColor(2, 0xd4ff00)
prettyLights.setZipLedColor(3, 0x5eff00)
prettyLights.setZipLedColor(4, 0x00bbff)
prettyLights.setZipLedColor(5, 0x9900ff)
prettyLights.setZipLedColor(6, 0xff3399)
prettyLights.show()
```

### Step 6
Click ``|Download|`` to program the BBC micro:bit with the code. All the ZIP LED's should each display a single colour. If the code has not worked correctly, go back and check the code with the tutorial hints.

### Step 7
Rather than having the ZIP LED's static, there are block that allow the set colours to move to the next ZIP LED position.  In the  ``||basic:forever loop||`` add a ``||kitronik_lab_bit.rotate ZIP LEDs by||`` block.  
This will move the colour of the ZIP LED's to the right by 1 position.  If they have reached the end the position will return back to the first ZIP LED position.
#### ~ tutorialhint
```blocks
let prettyLights: kitronik_lab_bit.ZIPString = null
basic.forever(function () {
    prettyLights.rotate(1)
})
```

### Step 8
Similar to the previous steps where the ZIP LED's have been changed, this change needs to have a show block after it.  See if you can remember which block it is and where it needs to go.
#### ~ tutorialhint
```blocks
let prettyLights: kitronik_lab_bit.ZIPString = null
basic.forever(function () {
    prettyLights.rotate(1)
    prettyLights.show()
})
```

### Step 9
Computers can process instructions (also known as algorithms) very quickly.  If we downloaded the code to the BBC micro:bit we would not see the changes being made, as the code would be looping around so quickly.  
To get around ``||basic:pause||`` after the ``||kitronik_lab_bit.show changes||`` block.  Depending what value of the pause is set to will alter how fast the positions move.  The bigger the pause the slowly the moving and visa-versa.  
In this example the pause will be set to 500milliseconds (or 0.5 seconds)
#### ~ tutorialhint
```blocks
let prettyLights: kitronik_lab_bit.ZIPString = null
basic.forever(function () {
    prettyLights.rotate(1)
    prettyLights.show()
    basic.pause(500)
})
```

### Step 10
Let's ``|Download|`` the code and see the rainbow colours move.

### Colour a rainbow tutorial complete @unplugged
Great job, you have succeeded in setting the ZIP LED's to different colours and make them switch positions.  You can take this code change the pause time to change the speed, or make the rotation by 1 to another number.  
This tutorial has been completed, however there are still loads of project that could be created.  
If you wish to know more on the Kitronik LAB:bit visit:  
http://www.kitronik.co.uk/56101
