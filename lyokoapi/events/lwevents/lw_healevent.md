---
description: Called when a LyokoWarrior receives HP
---

# LW\_HealEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/) and an `int`amount of HP gained

```csharp
LW_HealEvent.Call(LyokoWarriors.YUMI,10);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

Their [HP ](../../virtualentities/lyokowarrior/lyokowarrior.md#hp)will be raised with the given amount \(or until max\) 

{% hint style="danger" %}
If given a negative amount, it will instead call the [LW\_HurtEvent](lw_hurtevent.md).
{% endhint %}

