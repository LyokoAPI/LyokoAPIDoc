#APITower
This class is an implementation of [ITower](./Interfaces/ITower.md)

##Properties
Identical to [ITower](./Interfaces/ITower.md)
with the following differences:   
  * Activator has a public setter  
  * Activated returns true if the Activator is not NONE

##Constructors
This class has two constructors:
```csharp
APITower(int number, ISector sector);
```
this implies that the APITower belongs to an existing [ISector](./Interfaces/ISector.md).

```csharp
APITower(string vworld, string sector, int number);
```
This not only creates a new APITower, **but it also creates a new ISector with a new IVirtualWorld**
This means that the towers' vworld contains one sector, and that sector contains this tower.

##Equals()
This class has it's own Equals method.
However, it does not change the hash, so in a Hashmap or something similar, it will not follow the rules of Equals().

An object is equal to 'this' APITower if these conditions are true:
  * It's an ITower
  * It's ISector has the same name
  * It's IVirtualWorld has the same name
