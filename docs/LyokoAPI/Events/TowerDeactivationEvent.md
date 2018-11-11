#Tower Deactivation Event

##Subscribing
This event expects a ``void Method(ITower tower)``<br>
Since it uses an ITower, it's fairly read-only.

##Calling
You can call this event with an implementation of [ITower](../../VirtualStructures/Interfaces/ITower.md).  
That means you'll probably call it with APITower, like this:  
```csharp
TowerDeactivationEvent.Call(new APITower("lyoko","ice",1));
```
It will only be called if the ITower is actually deactivated.
