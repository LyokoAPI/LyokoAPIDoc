---
description: Called when a LyokoWarrior is devirtualized normally
---

# LW\_DevirtEvent

## Calling

To call this event, simply pass a `LyokoWarrior`.

```text
LW_DevirtEvent.Call(LyokoWarriors.WILLIAM);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

The LW's [Location](../../virtualentities/lyokowarrior/lyokowarrior.md#location) will be set to `APILocations.SCANNERS`, their [HP](../../virtualentities/lyokowarrior/lyokowarrior.md#hp) will be reset and their [Statuses ](../../virtualentities/lyokowarrior/lw_status.md)will be cleared and set to `LW_Status.EARTH`

{% hint style="info" %}
If the Lyokowarrior was the Rider or the Passenger of an [Overvehicle](../../virtualentities/overvehicle/overvehicle.md), it will be removed from the vehicle.
{% endhint %}



