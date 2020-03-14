---
description: Called when an overvehicle is devirtualized
---

# OV\_DevirtEvent

## Calling

To call this event, simply pass an [Overvehicle](../../virtualentities/overvehicle/overvehicle.md).

```text
OV_DevirtEvent.Call(Overvehicles.OVERWING);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

The OV's [Location](../../virtualentities/lyokowarrior/lyokowarrior.md#location) will be set to `APILocations.DEAD`, their [HP](../../virtualentities/overvehicle/overvehicle.md#hp) will be reset and their [Status ](../../virtualentities/overvehicle/ov_status.md)will be set to `OW_Status.DEVIRTUALIZED`

