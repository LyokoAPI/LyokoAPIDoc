---
description: Called when a Lyokowarrior is Frontiered
---

# LW\_FrontierEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/).

```csharp
LW_FrontierEvent.Call(LyokoWarriors.ODD);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

Their [Status ](../../virtualentities/lyokowarrior/lw_status.md)will be set to `LW_Status.FRONTIERED` and their [Location ](../../virtualentities/lyokowarrior/lyokowarrior.md#location)will be set to `APILocations.FRONTIER`

