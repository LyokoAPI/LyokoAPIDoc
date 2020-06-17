---
description: Called when a Virtual World gets deleted
---

# VirtualWorldDestructionEvent

## Calling

To call this event, simply pass a string or an [IVirtualWorld](../../virtualstructures/interfaces/ivirtualworld.md).

```csharp
VirtualWorldDestructionEvent.Call("Lyoko");
```

## Listening

You can use the [LAPIListener](../lapilistener.md) to listen to this event.

