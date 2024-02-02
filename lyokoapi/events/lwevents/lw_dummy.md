---
description: This event is called when a Lyokowarrior arrives at a location.
---

# LW\_ArriveEvent

## Calling&#x20;

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/) and a [location](../../realworld/location/abstract/ilocation.md). This can be any of the [LocationTypes](../../realworld/location/abstract/locationtype.md) (so you can also pass an [ISector](../../virtualstructures/interfaces/isector.md) for example)

```aspnet
LW_ArriveEvent.Call(LyokoWarriors.ODD,APILocations.ELEVATOR);
LW_ArriveEvent.Call(LyokoWarriors.YUMI,new APITower("Lyoko","ice",1));
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.
