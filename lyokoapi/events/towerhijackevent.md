---
description: >-
  This event is called when a tower goes from one activator to another. (for
  example, Hopper taking over a tower from XANA)
---

# TowerHijack Event

{% hint style="warning" %}
IFSCL currently doesn't implement this event well.
{% endhint %}

## Subscribing

This event expects a `void Method(Itower tower, APIActivator old, APIActivator new)`\
(see [APIActivator](https://github.com/LyokoAPI/LyokoAPIDoc/tree/fdb5e716f468c7556934771f257aae38e4ec78bc/docs/VirtualStructures/APIActivator/README.md) and [ITower](https://github.com/LyokoAPI/LyokoAPIDoc/tree/fdb5e716f468c7556934771f257aae38e4ec78bc/docs/VirtualStructures/Interfaces/ITower/README.md))

## Calling

To call this method, you need to supply the ITower, new APIActivator and old APIActivator.\
\
It will not, at this time, change the activator for you.
