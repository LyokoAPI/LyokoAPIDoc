---
description: Called when a Sector is deleted
---

# SectorDestructionEvent

## Calling

To call this event, simply pass the sector with strings, or an  [ISector](../../virtualstructures/interfaces/isector.md)

```csharp
SectorDestructionEvent.Call("Lyoko","Ice");
SectorDestructionEvent.Call(new APISector("Lyoko","Forest",10));
//Lyoko is the default virtual world
SectorDestructionEvent.Call("Forest");
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.
