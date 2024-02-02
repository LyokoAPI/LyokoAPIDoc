# APILocation

APILocation is an implementation of [ILocation](abstract/ilocation.md). It represents any location that only requires a `Name` property.

## Instantiating

You can instantiate an APILocation like this:

```csharp
//EXAMPLE! DONT DO THIS AS A PLUGIN DEVELOPER.
LW_ArriveEvent.Call(LyokoWarriors.ODD, new APILocation("The NorthPole"));
```

## Properties

### Name

Returns a `string`, being the name of the location.

## Methods

### [GetLocationName()](abstract/ilocation.md#getlocationname)

Returns [Name](apilocation.md##Name).

### [GetInnerLocation](abstract/ilocation.md#getinnerlocation)

Returns an instance of itself. (An APILocation doesn't have inner locations).

### [AsGenericLocation()](abstract/ilocation.md#asgenericlocation)
