# notlego

```package
pxt-nezha=github:elecfreaks/pxt-nezha
pxt-PlanetX=github:elecfreaks/pxt-planetx
```

## Case 01 The Pull Ups Robot
Show an icon of your choice using the micro:bit's LEDs.<br>
If Button A is pressed, run the motor at full speed.<br>
If Button B is pressed, stop the motor.

```blocks
input.onButtonPressed(Button.A, function () {
    neZha.setMotorSpeed(neZha.MotorList.M1, 100)
})
input.onButtonPressed(Button.B, function () {
    neZha.stopMotor(neZha.MotorList.M1)
})
basic.showIcon(IconNames.Heart)
```

## Case 14 The Gyro Launcher
Pseudo code here... BTW, press the lightbulb to see the example.

```blocks
neZha.setServoAngel(neZha.ServoTypeList._180, neZha.ServoList.S1, 160)
basic.forever(function () {
    if (PlanetX_Basic.Crash(PlanetX_Basic.DigitalRJPin.J1)) {
        neZha.setMotorSpeed(neZha.MotorList.M1, 100)
        neZha.setServoAngel(neZha.ServoTypeList._360, neZha.ServoList.S1, 210)
    } else {
        neZha.stopMotor(neZha.MotorList.M1)
        neZha.setServoAngel(neZha.ServoTypeList._360, neZha.ServoList.S1, 160)
    }
})
```

```ghost
let a = 0
input.onButtonPressed(Button.A, function () {
    neZha.setMotorSpeed(neZha.MotorList.M1, 100)
})
input.onButtonPressed(Button.B, function () {
    neZha.stopMotor(neZha.MotorList.M1)
})
basic.showIcon(IconNames.Heart)
input.onGesture(Gesture.Shake, function () {
    music.setVolume(127)
    music.play(music.builtinPlayableSoundEffect(soundExpression.giggle), music.PlaybackMode.UntilDone)
    music.play(music.tonePlayable(262, music.beat(BeatFraction.Whole)), music.PlaybackMode.UntilDone)
})
while ((true || false) == (false && false)) {
    music.play(music.stringPlayable("- - - - - - - - ", 120), music.PlaybackMode.UntilDone)
}
for (let index = 0; index < 1; index++) {
    music.stopAllSounds()
}
loops.everyInterval(500, function () {
    neZha.setServoSpeed(neZha.ServoList.S1, 0)
    if (PlanetX_Basic.Crash(PlanetX_Basic.DigitalRJPin.J1)) {
        neZha.setMotorSpeed(neZha.MotorList.M1, 100)
        neZha.setServoAngel(neZha.ServoTypeList._360, neZha.ServoList.S1, 210)
    } else {
        neZha.stopMotor(neZha.MotorList.M1)
        neZha.setServoAngel(neZha.ServoTypeList._360, neZha.ServoList.S1, 160)
    }
})
PlanetX_Basic.buttonEvent(PlanetX_Basic.DigitalRJPin.J1, PlanetX_Basic.ButtonStateList.C, function () {
    if (PlanetX_Basic.PIR(PlanetX_Basic.DigitalRJPin.J1)) {
        PlanetX_Basic.motorFan(PlanetX_Basic.DigitalRJPin.J1, false)
        PlanetX_Basic.laserSensor(PlanetX_Basic.DigitalRJPin.J1, false)
        while (PlanetX_Basic.noiseSensor(PlanetX_Basic.AnalogRJPin.J1) < PlanetX_Basic.ultrasoundSensor(PlanetX_Basic.DigitalRJPin.J1, PlanetX_Basic.Distance_Unit_List.Distance_Unit_cm)) {
            if (PlanetX_Basic.buttonCD(PlanetX_Basic.DigitalRJPin.J1, PlanetX_Basic.ButtonStateList.C)) {
                a = PlanetX_Basic.lightSensor(PlanetX_Basic.AnalogRJPin.J1)
                a = PlanetX_Basic.trimpot(PlanetX_Basic.AnalogRJPin.J1)
            }
        }
    }
})
```

## EXIT CONFIRMATION
Are you sure you're done?

## Don't press "Done" unless you're truly done! @showdialog