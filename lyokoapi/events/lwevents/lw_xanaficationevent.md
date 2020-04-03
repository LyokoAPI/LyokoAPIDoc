---
description: Called when a Lyokowarrior is xanafied
---

# LW\_XanaficationEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/).

```csharp
LW_XanaficationEvent.Call(LyokoWarriors.ODD);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

`LW_Status.XANAFIED` will be added to their [Statuses ](../../virtualentities/lyokowarrior/lw_status.md)

