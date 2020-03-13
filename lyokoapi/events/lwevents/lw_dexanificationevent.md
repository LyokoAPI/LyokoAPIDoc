---
description: Called when a Lyokowarrior is dexanafied
---

# LW\_DexanificationEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/).

```csharp
LW_DexanaficationEvent.Call(LyokoWarriors.ODD);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

Their [Status ](../../virtualentities/lyokowarrior/lw_status.md)will be set to `LW_Status.VIRTUALIZED`

