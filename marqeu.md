# marqeu

## Step 1
in this step we will be setting up the microbit to use the neopixal LED's 
and then setting the brightness  

```blocks
let counter = 0
let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)
strip.setBrightness(50)

## Step 2
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





## all the code
let counter = 0
let strip = neopixel.create(DigitalPin.P0, 13, NeoPixelMode.RGB)
strip.setBrightness(50)
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