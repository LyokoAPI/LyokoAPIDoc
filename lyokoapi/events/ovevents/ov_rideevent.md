---
description: Called when a Lyokowarrior starts riding an Overvehicle
---

# OV\_RideEvent

## Calling

To call this event, simply pass an [Overvehicle ](../../virtualentities/overvehicle/overvehicle.md)and a [LyokoWarrior](../../virtualentities/lyokowarrior/lyokowarrior.md).

```text
OV_RideEvent.Call(Overvehicles.OVERBOARD,LyokoWarriors.ODD);
OV_RideEvent.Call(Overvehicles.OVERBOARD,LyokoWarriors.AELITA);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

#### If the Overvehicle already has a Rider

The Lyokowarrior will be added as a [Passenger](../../virtualentities/overvehicle/overvehicle.md#warriorpassenger)

#### If the Overvehicle doesn't have a Rider

The Lyokowarrior will be added as a [Rider](../../virtualentities/overvehicle/overvehicle.md#warriorrider)

