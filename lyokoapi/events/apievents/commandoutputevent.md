---
description: This event is called whenever a command wants to send feedback to the user.
---

# Command Output Event

## Command class

The [Command class](../../commands/command.md) has a built in method to call this event.

## Calling

This event takes two Strings: the name of the command, and the message.

```csharp
string message = "music paused.";
CommandOutputEvent.Call("LyokoDJ",message);
```

The game will display it like this: `[LyokoDJ] music paused.`

## Listening

**Only application devs should listen to this event.**

{% tabs %}
{% tab title="Recommended method" %}
It's recommended to listen to this event with the [LAPIListener](../lapilistener.md)
{% endtab %}

{% tab title="DIY method" %}
```csharp
public class DIYListener
{
    public void StartListening()
    {
        CommandOutputEvent.Subscribe(OnCommand);
    }

    public void OnCommand(string command)
    {
        //do something with commandoutput, like showing it in-game
    }
}
```
{% endtab %}
{% endtabs %}

