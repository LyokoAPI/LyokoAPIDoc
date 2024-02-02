# Tower Activation Event

## Subscribing

This event expects a `void Method(ITower tower)`\
&#x20;Since it uses an ITower, it's fairly read-only.

## Calling

This events has a few parameters you can supply in Call().\
&#x20;There are important differences between them, so read carefully.\
&#x20;_Note: It will not be called if the supplied tower isn't activated._

### Call with [ITower](https://github.com/LyokoAPI/LyokoAPIDoc/tree/fdb5e716f468c7556934771f257aae38e4ec78bc/docs/VirtualStructures/Interfaces/ITower/README.md)

_Note: We don't generally recommend this._\
&#x20;You can call the event by supplying an implementation of ITower.\
&#x20;This assumes that the Activator is already set.\
&#x20;We only recommend this if you've chosen to base your Application's Tower class to implement ITower.

### Call with [APITower](https://github.com/LyokoAPI/LyokoAPIDoc/tree/fdb5e716f468c7556934771f257aae38e4ec78bc/docs/VirtualStructures/APITower/README.md), [APIActivator](https://github.com/LyokoAPI/LyokoAPIDoc/tree/fdb5e716f468c7556934771f257aae38e4ec78bc/docs/VirtualStructures/APIActivator/README.md)

_Hint: The benefit of this method is that you're not giving direct access to your own Tower class, if thats what you want._

You can call the event by supplying an APITower and an APIActivator.\
&#x20;There are many ways to do this, but you'll likely use the following:\


```csharp
TowerActivationEvent.Call(new APITower("Lyoko","ice",1),APIActivator.XANA)
```

Or, if you want to do it 'the hard way', you could also do:

```csharp
APITower tower = new APITower("Lyoko,ice,1")
TowerActivationEvent.Call(tower,APIActivator.XANA);
```

But in that case, you might as well use ITower as an argument.

This approach is almost identical to:

### Call with Strings

You can also call the event with only strings. Just like before, you won't be giving any access to your own tower class this way.

```csharp
TowerActivationEvent.Call("lyoko","ice",1,"XANA");
```

This **will** throw an exception if the activator is invalid, so make sure to get it right, or to put it in a try/catch.
