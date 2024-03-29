---
description: Called when a LyokoWarrior is virtualized.
---

# LW\_VirtEvent

## Calling&#x20;

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/) and the sector.

You can do this in a few ways:

```csharp
LW_VirtEvent.Call(LyokoWarriors.ODD,new APISector("Lyoko","ice");
LW_VirtEvent.Call(LyokoWarriors.ODD,"Lyoko","Ice");
LW_VirtEvent.Call(LyokoWarriors.ODD,"Ice"); //assumes Lyoko
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

`LW_Status.VIRTUALIZED`will be added to their [Statuses](../../virtualentities/lyokowarrior/lw\_status.md), and `LW_Status.EARTH` will be removed. Their [Location ](../../virtualentities/lyokowarrior/lyokowarrior.md#location)will be set to the given sector.\
Their [HP ](../../virtualentities/lyokowarrior/lyokowarrior.md#hp)will also be set to max.
