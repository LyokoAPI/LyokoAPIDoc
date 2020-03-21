---
description: This event is called when a Lyokowarrior is permanently killed.
---

# LW\_DeathEvent

## Calling

To call this event, simply pass a [Lyokowarrior](../../virtualentities/lyokowarrior/)

```text
LW_DeathEvent.Call(LyokoWarriors.ODD);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

The LW's [Location ](../../virtualentities/lyokowarrior/lyokowarrior.md#location)will be set to `APILocation.LOST` and their [Statuses ](../../virtualentities/lyokowarrior/lw_status.md)will be cleared and set to `LW_Status.DEAD`

