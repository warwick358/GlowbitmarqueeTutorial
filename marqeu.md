# marque

## Step 1 setup
We will start with setting up the microbit to use the neopixal LED's
in the blocks section click the "advanced" then click "extention" 
in this section you will need to select the neopixal extention

## step 2
Next we will create a variable calles "strip" click the "variable" tab
in the blocks then make a variable call it "strip".
go to the neopixal tab and get the ``||neopixal:set strip||`` block and place 
it in the "on start" block. 

```blocks
let strip = neopixel.create(DigitalPin.P0, 24, NeoPixelMode.RGB)

```

## step 3
make sure that the pin = "0" this is where we connect the wire on the microbit.
Then change the number of LED's to "13" this is how many lights we have on the GlowBit.
alos make sure the LED'd are set as "RGB" this is the tupe of light we have.

```blocks

let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)

```
## Step 4
In this step we will set the brightness to 50%. We will go to the "more" tab
under the "neopixal" tab. ``||neopixal:setBrightness||``


```blocks 
let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)
strip.setBrightness(50)
```

## Step 5
This is the last step for the "on start" block. 
Go the the "variable" tab abs select ``||variable:set||`` 
chose the variable counter.

```blocks
let counter = 0
let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)
strip.setBrightness(50)
```
## step 6 create the loop
we will now start working on the "forever' block.
In this section we will tell the microbit how to use the GlowBit's LED lights.
We will start with the "loop" tab. and look for a "for do" loop.
``||loop:for index do||`` 


```block
basic.forever(function () {
    for (let index = 0; index <= 12; index++) {
    	
    }
})

    ```

# step 7
we will then add a if statement to tell the microbit to use ever 3rd LED.
``||logic:if||`` 


```blocks
basic.forever(function () {
    for (let index = 0; index <= 12; index++) {
        if (true) {
        	
        }
    }
})
```
## step 8 adding information to the if statement 
Next we open the "logic" tab and scroll down to the comparison section we are looking 
for the "0=0" block and we will place it in the "true" part of the if ststement.
then we will open the "math" tab and find the "remainder of" block and replace the first 0
of the  "0=0" block.
then replace the frist 

```blocks
basic.forever(function () {
    for (let index = 0; index <= 13; index++) {
        if ((index - counter) % 3 == 0) {
            strip.setPixelColor(index, neopixel.colors(NeoPixelColors.Violet))
        }
    }
```


## all the code
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