#Tower Activation Event

##Subscribing
This event expects a ``void Method(ITower tower)``
Since it uses an ITower, it's fairly read-only.

##Calling
This events has a few parameters you can supply in Call()
There are important differences between them, so read carfully.

###Call with ITower
*note: we dont generally recommend this*
You can call the event by supplying an implementation of ITower.
This assumes that the Activator is already set.
We only recommend this if you've chosen to base your Applications Tower class to implement ITower.

###Call with APITower,APIActivator
You can call the event by supplying an APITower and an APIActivator.
There's many ways to do this, but you'll likely use:
The benefit is that you're not giving direct access to your own Tower class, if thats what you want.

``TowerActivationEvent.Call(new APITower("Lyoko","ice",1),APIActivator.XANA)``
or if you want to do it 'The hard way', you could also do:
```Java
APITower tower = new APITower("Lyoko,ice,1")
TowerActivationEvent.Call(tower,APIActivator.XANA);
```
But in that case, you might as well use ITower as an argument.

This approach is almost identical to:
###Call with strings
You can also call the event with only strings.
just like before, you wont be giving any access to your own tower class this way.
``TowerActivationEvent.Call("Lyoko","ice",1,"XANA");``
