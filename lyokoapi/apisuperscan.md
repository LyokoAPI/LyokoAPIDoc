# APISuperscan

APISuperscan is a helper class that contains some useful functions.  
 It's essentially a superscan that keeps track of the activated towers.  


You can get it with:

```csharp
APISuperscan superscan = APISuperscan.GetOrCreate();
```

As the name suggests, you will get either a new or an existing object.  
 This is to ensure that everyone has access to the same 'database'.  
 We recommend getting or creating the object at the very beggining of your code.

## Properties

The class contains 3 public lists:

XanaTowers

JeremieTowers

HopperTowers

You can get all towers \(that are active and that APISuperscan knows about\) with:

```csharp
IEnumerable alltowers = superscan.GetAllRegisteredTowers();
```

It also has a boolean `IsXanaAttacking`,   
 which is true if a [XanaAwakenEvent](events/annexevents/xanaawakenevent.md) has been logged \(by superscan\)  
 without a matching [XanaDefeatEvent](events/annexevents/xanadefeatevent.md).



