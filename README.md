# 2024-06-19 Project

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
```

## EXIT CONFIRMATION
Are you sure you're done?

## Don't press "Done" unless you're truly done! @showdialog