---
description: called when an Overvehicle is virtualized
---

# OV\_VirtEvent

## Calling

To call this event, simply pass an [Overvehicle ](../../virtualentities/overvehicle/overvehicle.md)and an [ISector ](../../virtualstructures/interfaces/isector.md)or a [Lyokowarrior](../../virtualentities/lyokowarrior/lyokowarrior.md).

```csharp
OV_VirtEvent.Call(Overvehicles.OVERBIKE);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

The OV's [Location ](../../virtualentities/overvehicle/overvehicle.md#location)will be set to the given ISector or the Lyokowarrior's [Location](../../virtualentities/lyokowarrior/lyokowarrior.md#location), their [HP](../../virtualentities/overvehicle/overvehicle.md#hp) will be reset and their [Status ](../../virtualentities/overvehicle/ov_status.md)will be set to `OV_Status.Virtualized`

