---
description: Called when a Lyokowarrior regains their Earth Codes
---

# LW\_CodeEarthResolvedEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/).

```csharp
LW_CodeEarthResolvedEvent.Call(LyokoWarriors.AELITA);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

`LW_Status.NOEARTHCODE` will be removed from their [Statuses ](../../virtualentities/lyokowarrior/lw_status.md)

