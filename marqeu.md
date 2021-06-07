# Marque

## step 1
To start we will create a variable called "strip" click the "variable" tab
In the blocks then make a variable call it "strip". 
Go to the "neopixal" tab and get the "set strip" block and place it in the "on start" block. 

```blocks
let strip = neopixel.create(DigitalPin.P0, 24, NeoPixelMode.RGB)

```

## step 2
Make sure that the pin = "0" this is where we connect the wire on the microbit.
Then change the number of LED's to "13" this is how many lights we have on the GlowBit.
alos make sure the LED'd are set as "RGB" this is the tupe of light we have.

```blocks

let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)

```

## Step 3
In this step we will set the brightness. LED's use a scale from 0 - 255 for brighness.
We will go to the "more" tab
under the "neopixal" tab and select the "setBrightness" block place it under the "set strip" block.
Change the number to 50.

```blocks 
let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)
strip.setBrightness(50)
```

## Step 4
This is the last step for the "on start" block. 
Go the the "variable" tab make a new variable "counter".
select the "set" block change the drop down to the variable "counter" leave the "0" as is. 

```blocks
let counter = 0
let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)
strip.setBrightness(50)
```

## step 5 create the loop
We will now start working on the "forever' block.
In this section we will tell the microbit how to use the GlowBit's LED lights.
We will start with the "loop" tab and look for a "for do" loop placce it in the forever loop. 
Change the number from "4" to "12"

```blocks
basic.forever(function () {
    for (let index = 0; index <= 12; index++) {
    	
    }
})
```

## step 6
We will then add a if statement to tell the microbit to use ever 3rd LED.
Go to the "logic" tab and get the "if true then" block place it in the "for do" loop. 

```blocks
basic.forever(function () {
    for (let index = 0; index <= 12; index++) {
        if (true) {
        	
        }
    }
})
```
## step 7 adding information to the if statement 
This is a complicate section so make sure your code matches the example before moving on.

Start by opening the "logic" tab and scroll down to the comparison section we are looking 
for the "0=0" block and we will place it in the "true" part of the if statement.

Then we will open the "math" tab and find the "remainder of" block. Place this block in the first "0" of the "0=0" block.

In the "remainder of" block  replace the first 0 of the  with another "math" block "0-0".

then replace the frist "0" with a "Variable" "index" and the second "0" with the "variable" "counter"

```blocks
basic.forever(function () {
    for (let index = 0; index <= 13; index++) {
        if ((index - counter) % 3 == 0) {
        }
    }
```

## step 8 setting the led colour
Go to the "neopixal more" tab and look for the "strip set pixal colour" block 
and put in the next section of the "if then" block.
change the "0" to the "variable" "index" and chose a colour in the drop down menu.

```block
basic.forever(function () {
    for (let index = 0; index <= 13; index++) {
        if ((index - counter) % 3 == 0) {
            strip.setPixelColor(index, neopixel.colors(NeoPixelColors.Violet))
        }
    }
```

## step 9 Displaying the LED's
In these last few steps we controll how fast the led's flash and make them display.
go to "basic" tab and chose the "pause" block Place it under the "if then" block.
set the pause to 200 miliseconds.
go to the "neopixal" tab and chose the "show strip" block and place it under the "pause block"
go to the "variable" tab and chose the "change" block (change the dropdown to "counter")
go to the "neopixal" tab and chose the "strip clear" block and place it under the "change" block

```block
let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)
strip.setBrightness(50)
let counter = 0
basic.forever(function () {
    for (let index = 0; index <= 13; index++) {
        if ((index - counter) % 3 == 0) {
            strip.setPixelColor(index, neopixel.colors(NeoPixelColors.Violet))
        }
    }
    basic.pause(200)
    strip.show()
    counter += 1
    strip.clear()
})
```

## step 10 check the code
your code should look lioke the example below and be ready to download to the Microbit.

```block

let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)
strip.setBrightness(50)
let counter = 0
basic.forever(function () {
    for (let index = 0; index <= 13; index++) {
        if ((index - counter) % 3 == 0) {
            strip.setPixelColor(index, neopixel.colors(NeoPixelColors.Violet))
        }
    }
    basic.pause(200)
    strip.show()
    counter += 1
    strip.clear()
})
```
