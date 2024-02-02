# APISuperscan

APISuperscan is a helper class that contains some useful functions.\
&#x20;It's essentially a superscan that keeps track of the activated towers.\


You can get it with:

```csharp
APISuperscan superscan = APISuperscan.GetOrCreate();
```

As the name suggests, you will get either a new or an existing object.\
&#x20;This is to ensure that everyone has access to the same 'database'.\
&#x20;We recommend getting or creating the object at the very beggining of your code.

## Properties

The class contains 3 public lists:

XanaTowers

JeremieTowers

HopperTowers

You can get all towers (that are active and that APISuperscan knows about) with:

```csharp
IEnumerable alltowers = superscan.GetAllRegisteredTowers();
```

It also has a boolean `IsXanaAttacking`, \
&#x20;which is true if a [XanaAwakenEvent](events/annexevents/xanaawakenevent.md) has been logged (by superscan)\
&#x20;without a matching [XanaDefeatEvent](events/annexevents/xanadefeatevent.md).

