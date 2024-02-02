---
description: Called when a Lyokowarrior dismounts an Overvehicle
---

# OV\_GetOffEvent

## Calling

To call this event, simply pass an [Overvehicle ](../../virtualentities/overvehicle/overvehicle.md)and a [LyokoWarrior](../../virtualentities/lyokowarrior/lyokowarrior.md).

```csharp
OV_GetOffEvent.Call(Overvehicles.OVERBOARD,LyokoWarriors.ODD);
OV_GetOffEvent.Call(Overvehicles.OVERBOARD,LyokoWarriors.AELITA);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

#### If the warrior was the Passenger

The Lyokowarrior will be removed as [Passenger](../../virtualentities/overvehicle/overvehicle.md#warriorpassenger).

#### If the Overvehicle was the Rider

The Lyokowarrior will be removed as a [Rider](../../virtualentities/overvehicle/overvehicle.md#warriorrider).\
If the Overvehicle has a [Passenger](../../virtualentities/overvehicle/overvehicle.md#warriorpassenger), it will become the [Rider](../../virtualentities/overvehicle/overvehicle.md#warriorrider).

{% hint style="warning" %}
This event is not called if the Rider or Passenger gets devirtualized, but they will be removed from the vehicle.
{% endhint %}
