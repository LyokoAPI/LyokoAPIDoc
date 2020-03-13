---
description: Called when a Lyokowarrior takes damage
---

# LW\_HurtEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/) and an `int`amount of damage.

```csharp
LW_HurtEvent.Call(LyokoWarriors.YUMI,10);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

Their [HP ](../../virtualentities/lyokowarrior/lyokowarrior.md#hp)will be lowered with the given amount \(or until 0\).

{% hint style="warning" %}
The [LW\_DevirtEvent](lw_devirtevent.md) is not called when the HP drops to 0
{% endhint %}

{% hint style="danger" %}
If given a negative amount, it will instead call the[ LW\_HealEvent](lw_healevent.md).
{% endhint %}

