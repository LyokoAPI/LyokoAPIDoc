---
description: Called when a Lyokowarrior is Frontiered
---

# LW\_FrontierEvent

## Calling&#x20;

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/).

```csharp
LW_FrontierEvent.Call(LyokoWarriors.ODD);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

`LW_Status.FRONTIERED` will be added to their [Statuses](../../virtualentities/lyokowarrior/lw\_status.md), [**LW\_DexanaficationEvent**](lw\_dexanificationevent.md) **will be called if necessary** and their [Location ](../../virtualentities/lyokowarrior/lyokowarrior.md#location)will be set to `APILocations.FRONTIER`
