# LyokoWarrior

## LyokoWarrior

Lyokowarrior is a class that represents..a Lyokowarrior \(I mean, come on\).

This object will be passed by LW events. To get the info on a specific LW, use the [LyokoWarriors](https://github.com/LyokoAPI/LyokoAPIDoc/tree/a5b2e71d661b5e232a313d2e947906767206bc6f/docs/LyokoAPI/VirtualEntities/LyokoWarrior/Lyokowarriors.md) 'enum'-ish class.

## Properties

### [LyokoWarriorName](lyokowarriorname.md)

### [Location](../../realworld/location/genericlocation.md)

### [Status](lw_status.md)

### HP

The `int` HP \('Health Points'\) describes the health of the Lyokowarrior. It's a number between `0` and `MAX_HP`, which is equal to `100`.

To see if a LW is dead, it is better to check the [Status](lw_status.md)

## Methods

### IsRidingVehicle\(\)

This method returns a `boolean`. This boolean is `true` if the warrior is riding an [Overvehicle](../overvehicle/overvehicle.md).

### GetVehicle\(\)

This method returns the [Overvehicle ](../overvehicle/overvehicle.md#dummy)that the Lyokowarrior is riding, or `null`.

