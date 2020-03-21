---
description: Called when a LW's DNA is corrupted
---

# LW\_DNACorruptionEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/).

```csharp
LW_DNACorruptionEvent.Call(LyokoWarriors.ODD);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

`LW_Status.DNACORRUPTED` will be added to their [Statuses ](../../virtualentities/lyokowarrior/lw_status.md)

