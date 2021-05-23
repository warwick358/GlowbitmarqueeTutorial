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


## all the code
let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)
strip.setBrightness(50)
let counter = 0
basic.forever(function () {
    for (let index = 0; index <= 12; index++) {
        if ((index - counter) % 3 == 0) {
            strip.setPixelColor(index, neopixel.colors(NeoPixelColors.Violet))
        }
    }
    basic.pause(200)
    strip.show()
    counter += 1
    strip.clear()
})