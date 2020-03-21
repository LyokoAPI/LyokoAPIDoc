---
description: Called when a LW's DNA is no longer corrupted
---

# LW\_FixedDNAEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/).

```csharp
LW_FixedDNAEvent.Call(LyokoWarriors.ODD);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

`LW_Status.DNACORRUPTED` will be removed from their [Statuses ](../../virtualentities/lyokowarrior/lw_status.md)

