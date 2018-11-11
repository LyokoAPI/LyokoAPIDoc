#APISector
This class implements [ISector](./Interfaces/ISector.md)

##Properties
Identical to [ISector](./Interfaces/ISector.md)

##Constructors
This class has two constructors:

```csharp
APISector(IVirtualWorld world, string name, int towers = 0);
```
This implies that the sector belongs to an existing [IVirtualWorld](./Interfaces/IVirtualWorld.md).  
if you supply an ammount of towers, they will be created automatically,
starting from 1 until the ammount given.  
**The sector will be automatically added to the Vworld if not already present**  
Example:
```csharp
IVirtualWorld Lyoko = new APIVirtualWorld("lyoko");
ISector iceSector = new APISector(Lyoko,"ice",10);
```
***
You can also use a string for the virtualworld:
```csharp
APISector(string virtualworldname, string sectorname, int towers = 0);
```
This constructor will do the same thing as the one above, except it will create a new [IVirtualWorld](./Interfaces/IVirtualWorld.md)