---
description: This event is called whenever a command is executed in the game.
---

# Command Input Event

{% hint style="success" %}
The commands can be prefixed by "api.", but LAPI automatically removes it before passing it to the plugins.
{% endhint %}

{% hint style="danger" %}
**As usual, only application devs should call this event, DO NOT call this from your plugin**
{% endhint %}

## Calling

This event takes a String, being the complete command (either with or without the "api." prefix)

```csharp
string myCommand = "api.plugins.list";
CommandInputEvent.Call(myCommand);
```

## CommandListener

It's highly recommend for plugin developers to use the [CommandListener](../../commands/commandlistener.md) to work with commands
