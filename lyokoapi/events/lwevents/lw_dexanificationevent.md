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

`LW_Status.XANAFIED` or  `LW_Status.PERMXANAFIED` will be removed from their [Statuses ](../../virtualentities/lyokowarrior/lw_status.md)

{% hint style="info" %}
[LW\_FrontierEvent](lw_frontierevent.md) will call this event if necessary.
{% endhint %}



