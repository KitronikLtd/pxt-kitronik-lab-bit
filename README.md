
> Open this page at [https://kitronikltd.github.io/pxt-kitronik-lab-bit/](https://kitronikltd.github.io/pxt-kitronik-lab-bit/)

## Use as Extension

This repository can be added as an **extension** in MakeCode.

* open [https://makecode.microbit.org/](https://makecode.microbit.org/)
* click on **New Project**
* click on **Extensions** under the gearwheel menu
* search for **https://github.com/kitronikltd/pxt-kitronik-lab-bit** and import

# Online Tutorials

Using the MakeCode Tutorial tool, there are 7 tutorials to work through that will give examples of all the different inputs and outputs usable on the LAB:bit

[Tutorial - Make a Dice](https://makecode.microbit.org/#tutorial:github:kitronikltd/pxt-kitronik-lab-bit/Tutorial_A_Make_A_Dice)
Using the blocks create an electronics dice

[Tutorial - Create a switch](https://makecode.microbit.org/#tutorial:github:kitronikltd/pxt-kitronik-lab-bit/Tutorial_B_Create_A_Switch)
With a mixture of coding and materials create a switch

[Tutorial - Colour a rainbow](https://makecode.microbit.org/#tutorial:github:kitronikltd/pxt-kitronik-lab-bit/Tutorial_C_Colour_a_rainbow)
Colour the RGB LED's to make all the colours of the rainbow

[Tutorial - Traffic light sequence](https://makecode.microbit.org/#tutorial:github:kitronikltd/pxt-kitronik-lab-bit/Tutorial_D_Traffic_light_sequence)
Learning how to create sequence with an example of a Traffic LightShow

[Tutorial - Speed Control](https://makecode.microbit.org/#tutorial:github:kitronikltd/pxt-kitronik-lab-bit/Tutorial_E_Speed_control)
Control the onboard motor with a varying input

[Tutorial - Scare the micro:bit](https://makecode.microbit.org/#tutorial:github:kitronikltd/pxt-kitronik-lab-bit/Tutorial_F_Scare_the_microbit)
Using the microphone input to see if you can scare the micro:bit

[Tutorial - Parking sensor](https://makecode.microbit.org/#tutorial:github:kitronikltd/pxt-kitronik-lab-bit/Tutorial_G_Parking_sensor)
Beep Beep.. parking your LAB:bit with the use of the ultrasonic sensor


# pxt-kitronik-lab-bit Blocks

Custom blocks for www.kitronik.co.uk/56101 Kitronik LAB:bit.  There are easy to use blocks to take full usage of all the input and output hardward on the product.
Below are a list of the different blocks and their functions.

## readAnalogInput()
```blocks
kitronik_lab_bit.readAnalogInput()
```
Function will read the analog input from the on board potentiometer.  The value is converted to a 0-100 scale

## measureCm()
```blocks
kitronik_lab_bit.measureCm()
```
Taking a distance messurement from the ultrasonic sensor.  The returned value is the distance in centimetres.

## measureIn()
```blocks
kitronik_lab_bit.measureIn()
```
Taking a distance messurement from the ultrasonic sensor.  The returned value is the distance in inches.

## readScaledSoundLevel()
```blocks
kitronik_lab_bit.readScaledSoundLevel()
```
Reading the single microphone at the point of the block being called. Measurement will be a value between 0-100

## readScaledAverageSoundLevel()
```blocks
kitronik_lab_bit.readScaledAverageSoundLevel()
```
Reading an average microphone reading over 5 points.  Extra reading will be taken at the point of the block being called. Measurement will be a value between 0-100

## listenForClap()
```blocks
kitronik_lab_bit.listenForClap(claps: number, timerperiod: number, soundSpike_handler: Action)
```
Action function will execute the code in handler. Function will run when the required number of claps have been detected within a given a time period.

## trafficLightShow()
```blocks
basic.forever(function () {
    kitronik_lab_bit.trafficLightShow(
    kitronik_lab_bit.TrafficLight.one,
    0xff0000,
    0xffff00,
    0x00ff00
    )
})
```
Traffic light block will control the deicated LED's on the LAB:bit board.  Selection of colours determines whether the LED is on or off.  The block will allow the selection of which traffic light is controlled.

## trafficLightOff()
```blocks
kitronik_lab_bit.trafficLightOff(kitronik_lab_bit.TrafficLight.one)
```
Basic block that will switch off the LED's on the selected traffic light

## diceShow()
```blocks
kitronik_lab_bit.showDiceNumber(1)
```
Function will control the LED driver to show the standard dice patterns on the dice LED's

## showDiceNumber()
```blocks
kitronik_lab_bit.showDiceNumber(0)
```
Block will use all 9 dice led's on the LAB:bit board with the aim to create number digits on the dice LED's

## diceOff()
```blocks
kitronik_lab_bit.diceOff()
```
Calling function will turn off all the LED's on the dice area of the LAB:bit board

## ZIP String LED's
## createZIPString()
```blocks
prettyLights = kitronik_lab_bit.createZIPString(7)
```
Block is require to set the ZIP LED's to a variable and be able to be controlled with the other block functions within the extension

## setBrightness()
```blocks
prettyLights.setBrightness(kitronik_lab_bit.ZipLedBrightness.Dim)
```
Function give the user the ability to change the brightness of the ZIP LED's from a drop down selection for ease of options. Requires the show function after to see the changes.

## showRainbow()
```blocks
prettyLights.showRainbow()
```
Will set the ZIP LED's to show a rainbow effect across the LED's with an even spread of colour over the 7 LED's

## rotate()
```blocks
prettyLights.rotate(1)
```
Rotate block will move the current settings of the LED's by the given number within the block.

## setBrightnessPercent()
```blocks
prettyLights.setBrightnessPercent(0)
```
Alter the brightness from a percentage input. Requires the show function after to see the changes.

## clear()
```blocks
prettyLights.clear()
```
Clear all the current setting on the ZIP LED's.  Requires the show function after to see the changes.

## showBarGraph()
```blocks
prettyLights.showBarGraph(0, 100)
```
The bar graph function will plot a variable onto the ZIP LED's and upto a value of 100.

## setZipLedColor()
```blocks
prettyLights.setZipLedColor(0, 0xd4ff00)
```
Function will allow the user to set a deicated LED position to a particular colour from the colour palette selection. Requires the show function after to see the changes.

## show()
```blocks
prettyLights.show()
```
Show function is used to show any changes to the ZIP LED's within the code.

## showColor()
```blocks
prettyLights.showColor(0xd4ff00)
```
Block will set all the ZIP LED's to the same colour.  Colour is selected from using the colour pallete selection tool.

## motorOn()
```blocks
kitronik_lab_bit.motorOn(kitronik_lab_bit.MotorDirection.CW, 0)
```
Will turn on the motor on the LAB:bit board.  With selection of directions from a drop down list and a numeric input for the speed between 0-100.

## motorOff()
```blocks
kitronik_lab_bit.motorOff()
```
Function turns off the motor output.

## Advanced blocks
## diceLED()
```blocks
kitronik_lab_bit.diceLED(kitronik_lab_bit.DiceLocation.TL, kitronik_lab_bit.LightShow.On)
```
Block allows the each LED's on the dice to be controlled individually and being able to turn them on and off

## readRawAnalogInput()
```blocks
kitronik_lab_bit.readRawAnalogInput()
```
Will take an analog reading from the on board potentiometer and return back a reading between 0-1023

## readSoundLevel()
```blocks
kitronik_lab_bit.readSoundLevel()
```
Reading the single microphone at the point of the block being called. Measurement will be a value between 0-512

## readAverageSoundLevel()
```blocks
kitronik_lab_bit.readAverageSoundLevel()
```
Reading an average microphone reading over 5 points.  Extra reading will be taken at the point of the block being called. Measurement will be a value between 0-512

## setClapSensitivity()
```blocks
kitronik_lab_bit.setClapSensitivity(80)
```
Block can be used to alter the sensitivity of the microphone readings.
