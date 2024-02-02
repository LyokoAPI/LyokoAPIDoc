# CommandListener

## CommandListener

The CommandListener class is a special LAPIListener class. It's designed for use with [ICommand](icommand.md)s.

## Instatiating

To make a new CommandListener, simply extend it, and assign the Prefix:

```csharp
public class MyCommandListener : CommandListener
{
    protected override string Prefix {get;} = "dj";
}
```

The prefix is the main command of your plugin. LyokoDJ has the `dj` prefix, for example.

## Adding commands

You can add commands by calling the `AddCommand()` method, either inside or outside the class. The method returns a `CommandListener`, so you can chain the additions.

```csharp
public class MyCommandListener : CommandListener
{
    protected override string Prefix {get;} = "dj";
    public MyCommandListener()
    {
        AddCommand(new PlayCommand());
        AddCommand(new PauseCommand());
    }
}
```

## Listening for commands

To start listening for commands, call the StartListening method from [LAPIListener](https://github.com/LyokoAPI/LyokoAPIDoc/tree/39a56c357fb84779fa832cca91622a2eb6f63ae6/docs/LyokoAPI/Commands/LyokoAPI/Events/LAPIListener.md):

```csharp
public class MyPlugin : LyokoAPIPlugin
{
    //...
    private MyCommandListener commandListener = new MyCommandListener();
    protected override bool OnEnable()
    {
        commandListener.StartListening()
    }
    protected override bool OnDisable()
    {
        commandListener.StopListening();
    }
    //...
}
```

**Don't forget about the** [**Rules**](https://github.com/LyokoAPI/LyokoAPIDoc/tree/39a56c357fb84779fa832cca91622a2eb6f63ae6/docs/LyokoAPI/Commands/LyokoPlugin/introduction.md)
