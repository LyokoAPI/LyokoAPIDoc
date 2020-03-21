# LW\_DeTranslationEvent

## Calling 

To call this event, you need to pass a [LyokoWarrior](../../virtualentities/lyokowarrior/) and a [location](../../realworld/location/abstract/ilocation.md). This can only be an [ISector](../../virtualstructures/interfaces/isector.md).

```csharp
LW_DeTranslationEvent.Call(LyokoWarriors.ODD,new APISector("ForestReplika","Forest"));
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

## Effects

`LW_Status.TRANSLATED` will be removed from their [Statuses ](../../virtualentities/lyokowarrior/lw_status.md)and their [Location ](../../virtualentities/lyokowarrior/lyokowarrior.md#location)will be set to the given location.

