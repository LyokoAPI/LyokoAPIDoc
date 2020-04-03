---
description: Called when a LyokoWarrior is Translated
---

# LW\_TranslationEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/) and a [location](../../realworld/location/abstract/ilocation.md). This can only be an [APILocation](../../realworld/location/apilocation.md).

```csharp
LW_TranslationEvent.Call(LyokoWarriors.ODD,new APILocation("Mountain Lab"));
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

`LW_Status.TRANSLATED` will be added to their [Statuses ](../../virtualentities/lyokowarrior/lw_status.md)and their [Location ](../../virtualentities/lyokowarrior/lyokowarrior.md#location)will be set to the given location.

