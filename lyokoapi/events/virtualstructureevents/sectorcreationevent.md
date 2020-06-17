---
description: Called when a sector is created
---

# SectorCreationEvent

## Calling

To call this event, simply pass the world \(string\), sector \(string\) and the amount of towers if it isn't 10 \(int\)

You can also pass an [ISector](../../virtualstructures/interfaces/isector.md)

```csharp
//make Lyoko's Ice sector with 10 towers
SectorCreationEvent.Call("Lyoko","Ice");
//Default world is Lyoko
SectorCreationEvent.Call("Forest");
//Specifying the towers
SectorCreationEvent.Call("Carthage",1);
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

