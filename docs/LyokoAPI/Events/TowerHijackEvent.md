#TowerHijack Event
This event is called when a tower goes from one activator to another.<br>
(for example, Hopper taking over a tower from XANA)

##Subscribing
This event expects a
``void Method(Itower tower, APIActivator old, APIActivator new)``  
(see [APIActivator](../../VirtualStructures/APIActivator) and [ITower](../../VirtualStructures/Interfaces/ITower))

##Calling
To call this method, you need to supply the ITower, new APIActivator and old APIActivator.<br>  
It will not, at this time, change the activator for you.
