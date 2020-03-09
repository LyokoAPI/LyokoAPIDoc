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

The LW's [Location](../../virtualentities/lyokowarrior/lyokowarrior.md#location) will be set to `APILocations.SCANNERS`, their [HP](../../virtualentities/lyokowarrior/lyokowarrior.md#hp) will be reset and their [Status ](../../virtualentities/lyokowarrior/lw_status.md)will be set to `LW_Status.EARTH`



