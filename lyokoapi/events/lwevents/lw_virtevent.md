---
description: Called when a LyokoWarrior is virtualized.
---

# LW\_VirtEvent

## Calling 

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

Their [Status ](../../virtualentities/lyokowarrior/lw_status.md)will be set to `LW_Status.VIRTUALIZED` and their [Location ](../../virtualentities/lyokowarrior/lyokowarrior.md#location)will be set to the given sector.  
Their [HP ](../../virtualentities/lyokowarrior/lyokowarrior.md#hp)will also be set to max.

