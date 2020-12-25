# TowerHijack Event

This event is called when a tower goes from one activator to another.  
 \(for example, Hopper taking over a tower from XANA\)

## Subscribing

This event expects a `void Method(Itower tower, APIActivator old, APIActivator new)`  
\(see [APIActivator](https://github.com/LyokoAPI/LyokoAPIDoc/tree/87c9dac8253d28d7c075a9d7d2f881dc75f76a21/docs/VirtualStructures/APIActivator/README.md) and [ITower](https://github.com/LyokoAPI/LyokoAPIDoc/tree/87c9dac8253d28d7c075a9d7d2f881dc75f76a21/docs/VirtualStructures/Interfaces/ITower/README.md)\)

## Calling

To call this method, you need to supply the ITower, new APIActivator and old APIActivator.  
  
It will not, at this time, change the activator for you.

