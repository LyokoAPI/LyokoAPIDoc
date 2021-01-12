---
description: Represents a virtual vehicle.
---

# Overvehicle

This object will be passed by OV events. To get the info on a specific OV, use the [Overvehicles](overvehicles.md) 'enum'-ish class.

## Properties

### [OverVehicleName](overvehiclename.md)

### [Location](../../realworld/location/genericlocation.md)

### [Status](ov_status.md)

### HP

The `int` HP \('Health Points'\) describes the health of the Overvehicle. It's a number between `0` and `MAX_HP`, which is equal to `100`.

To see if a OV is devirtualized, it is better to check the [Status](ov_status.md)

### WarriorRider

The [LyokoWarrior ](../lyokowarrior/lyokowarrior.md)that is riding the Overvehicle.

### WarriorPassenger

The [LyokoWarrior ](../lyokowarrior/lyokowarrior.md)that is the OV's passenger.

