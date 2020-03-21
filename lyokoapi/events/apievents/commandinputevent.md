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

This event takes a String, being the complete command \(either with or without the "api." prefix\)

```csharp
string myCommand = "api.plugins.list";
CommandInputEvent.Call(myCommand);
```

## CommandListener

It's highly recommend for plugin developers to use the [CommandListener](https://github.com/LyokoAPI/LyokoAPIDoc/tree/fdb5e716f468c7556934771f257aae38e4ec78bc/docs/LyokoAPI/Events/APIEvents/LyokoAPI/Commands/CommandListener.md) to work with commands

