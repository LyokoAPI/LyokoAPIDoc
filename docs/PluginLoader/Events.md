#Introduction
If your application has a concept of Games or Game Sessions,
the LyokoPluginLoader provides two events to let the plugins know of the state of the current Session.

Learn more about Events: [EventSummary](../LyokoAPI/Events/EventSummary.md)
#GameStartEvent
This event is to signify that a game-session has started.

##Calling
You can call the event with
```csharp
GameStartEvent.Call(bool story = false);
```
The boolean ``story`` sigifies wether or not the game-session is a 'story-mode'. What this means is largely application-dependant. <br>
See [LyokoPlugin](../LyokoPlugin/introduction.md) for more info.

##Subscribing
The event is mostly used by the PluginLoader, but if you want to use it in your own Application, you can.
```csharp
GameStartEvent.Subscribe(void Method(bool story))
```
