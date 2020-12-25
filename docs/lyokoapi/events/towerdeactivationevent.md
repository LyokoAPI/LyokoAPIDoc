# Tower Deactivation Event

## Subscribing

This event expects a `void Method(ITower tower)`  
 Since it uses an ITower, it's fairly read-only.

## Calling

You can call this event with an implementation of [ITower](https://github.com/LyokoAPI/LyokoAPIDoc/tree/87c9dac8253d28d7c075a9d7d2f881dc75f76a21/docs/VirtualStructures/Interfaces/ITower/README.md).  
 That means you'll probably call it with APITower, like this:

```csharp
TowerDeactivationEvent.Call(new APITower("lyoko","ice",1));
```

It will only be called if the ITower is actually deactivated.

