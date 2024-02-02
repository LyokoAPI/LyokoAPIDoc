# APISector

## APISector

This class implements [ISector](interfaces/isector.md)

## Properties

Identical to [ISector](interfaces/isector.md)

## Constructors

This class has two constructors:

```csharp
APISector(IVirtualWorld world, string name, int towers = 0);
```

This implies that the sector belongs to an existing [IVirtualWorld](interfaces/ivirtualworld.md).\
&#x20;If you supply an amount of towers, they will be created automatically,\
&#x20;starting from 1 until the given amount.\
**The sector will be automatically added to the VirtualWorld if not already present**\
Example:

```csharp
IVirtualWorld Lyoko = new APIVirtualWorld("lyoko");
ISector iceSector = new APISector(Lyoko,"ice",10);
```

You can also use a string for the VirtualWorld:

```csharp
APISector(string virtualworldname, string sectorname, int towers = 0);
```

This constructor will do the same thing as the one above, except it will create a new [IVirtualWorld](interfaces/ivirtualworld.md)

## Methods

### \[GetLocationName()]\(../RealWorld/Location/Abstract/ILocation.md#GetLocationName())

For the Sector `Lyoko Ice`: `"Lyoko : Ice"`

### \[GetInnerLocation]\(../RealWorld/Location/Abstract/ILocation.md#GetInnerLocation())

Returns itself.
