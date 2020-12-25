# ITower

An interface representing a Tower on a VirtualWorld

## Properties

* Number - the number of the ITower.
* Activated - whether or not the ITower is activated. Preferably this is `!= APIActivator.NONE`   
* Sector - the [ISector](isector.md) this ITower is a member of. 
* Activator - the current [APIActivator](../apiactivator.md) that this tower is under control of.

## Notes

ITower does not have a public setter on Activator, so if it is used through the interface, like so:

```csharp
ITower tower = new APITower("lyoko","ice","1");
```

You can't change its Activator directly.  
  
You can access the full location of the ITower by getting the ISector and its IVirtualWorld.  
  
_Hint: If the implementation is APITower, it's not guaranteed that the Sector and the VirtualWorld have other data besides the tower. See_ [_APITower_](../apitower.md) _for more information._

