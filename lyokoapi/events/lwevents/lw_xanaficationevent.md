---
description: Called when a Lyokowarrior is xanafied
---

# LW\_XanaficationEvent

{% hint style="warning" %}
Permanent Xanafication is currently not implemented in LAPI.
{% endhint %}

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/).

```csharp
LW_XanaficationEvent.Call(LyokoWarriors.ODD);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

Their [Status ](../../virtualentities/lyokowarrior/lw_status.md)will be set to `LW_Status.XANAFIED`

