#Xana Awaken Event
This event is called when xana starts his attack.
It also provides the tower it started the attack with.
*note: It's called by APISuperscan if it has been created.*

##Subscribing
This event expects a ``void Method(Itower)``
The [ITower](../../VirtualStructures/Interfaces/Itower.md) is the one that initiated the attack.

##Subscribing
To call this event, you need to supply the ITower that started the attack.
