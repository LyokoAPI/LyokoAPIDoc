#TowerHijack Event
This event is called when a tower goes from one activator to another
(for example, Hopper taking over a tower from XANA)

##Subscribing
This event expects a
``void Method(Itower tower, APIActivator old, APIActivator new)``
(see [APIActivator](../../VirtualStructures/APIActivator.md) and [ITower](../../VirtualStructures/Interfaces/ITower.md))

##Calling
To call this method, you need to supply the ITower, new APIActivator and old APIActivator.
It will not, at this time, change the activator for you.
