# Command Output Event

This event is called whenever a command wants to send feedback to the user.

## Command class

The [Command class](https://github.com/LyokoAPI/LyokoAPIDoc/tree/fdb5e716f468c7556934771f257aae38e4ec78bc/docs/LyokoAPI/Events/APIEvents/LyokoAPI/Commands/Command.md) has a built in method to call this event.

## Calling

This event takes two Strings: the name of the command, and the message.

```csharp
string message = "music paused.";
CommandOutputEvent.Call("LyokoDJ",message);
```

The game will display it like this: `[LyokoDJ] music paused.`

## Listening

This event supplies a string, being the complete output including the name of the sending command.

**Only application devs should listen to this event.**

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

