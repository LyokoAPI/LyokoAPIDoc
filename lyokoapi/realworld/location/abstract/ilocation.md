# ILocation

## ILocation

ILocation is a Generic interface that describes a location.

## Methods

### GetLocationName\(\)

Returns a string, being the name of the ILocation.

### GetInnerLocation\(\)

Returns the actual location of the ILocation. For example if the ILocation is a [ISector](../../../virtualstructures/interfaces/isector.md), it will return the ISector.

### AsGenericLocation\(\)

Returns a [GenericLocation](../genericlocation.md) for this location.

