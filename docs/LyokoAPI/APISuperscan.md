#APISuperscan
APISuperscan is a helper class that contains some useful functions.<br>
It's essentially a superscan that keeps track of the activated towers.<br>

You can get it with:
```csharp
APISuperscan superscan = APISuperscan.GetOrCreate();
```
As the name suggests, you will get either a new or an existing object.<br>
This is to ensure that everyone has access to the same 'database'.<br>
We recommend getting or creating the object at the very beggining of your code.

##Properties
The class contains 3 public lists:<br>
  * XanaTowers
  * JeremieTowers
  * HopperTowers

You can get all towers (that are active and that APISuperscan knows about) with:
```csharp
IEnumerable alltowers = superscan.GetAllRegisteredTowers();
```

It also has a boolean ``IsXanaAttacking``, <br>
which is true if a [XanaAwakenEvent](./Events/XanaAwakenEvent.md) has been logged (by superscan)<br>
without a matching [XanaDefeatEvent](./Events/XanaDefeatEvent.md).
