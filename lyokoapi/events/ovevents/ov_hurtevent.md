---
description: Called when an overvehicle recieves damage
---

# OV\_HurtEvent

## Calling

To call this event, simply pass an [Overvehicle](../../virtualentities/overvehicle/overvehicle.md) and the damage as an `int`.

```csharp
OV_HurtEvent.Call(Overvehicles.OVERWING,10);
```

{% hint style="info" %}
LAPI will refuse to deal negative damage.
{% endhint %}

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

The OV's [HP ](../../virtualentities/overvehicle/overvehicle.md#hp)will be lowered with the given amount, or until 0.
