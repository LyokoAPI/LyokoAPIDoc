#ITower
An interface representing a Tower on a Virtualworld

##Properties
Number - the number of the ITower  
Activated - wether or not the ITower is activated. Preferably this is != APIActivator.NONE  
Sector - the [ISector](./ISector.md) this ITower is a member of.  
Activator - the current [APIActivator](../../VirtualStructures/APIActivator.md) that this tower is under control of.

##Notes
ITower does not have a public setter on Activator, so if it is used through the interface,
like so:
```csharp
ITower tower = new APITower("lyoko","ice","1");
```
You can not change its Activator directly.  
You can access the full location of the ITower by getting the ISector and it's IVirtualWorld.  
*hint: if the implementation is APITower, it's not guaranteed that the sector and virtualworld have other data besides the tower.
See APITower for more information.*
