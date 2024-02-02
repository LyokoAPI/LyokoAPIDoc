# Introduction

If your application has a concept of Games or Game Sessions, the LyokoPluginLoader provides two events to let the plugins know of the state of the current Session.

Learn more about Events: [EventSummary](broken-reference)

## GameStartEvent

This event is to signify that a game-session has started.

You can call the event with:

```csharp
GameStartEvent.Call(bool story = false);
```

The boolean `story` signifies whether or not the game-session is a 'story-mode'. What this means is largely application-dependant. \
&#x20;It's false unless stated otherwise.

## See [LyokoPlugin](../lyokoplugin/introduction.md) for more info.

The event is mostly used by the PluginLoader, but if you want to use it in your own Application, you can.

```csharp
GameStartEvent.Subscribe(void Method(bool story))
```

## GameEndEvent

This event is to signify that a game-session has ended. \
&#x20;You can call it with:

```csharp
GameEndEvent.Call(bool failed)
```

The boolean `failed` signifies whether or not the user lost the game.

## See [LyokoPlugin](../lyokoplugin/introduction.md) for more info.

The event is mostly used by the PluginLoader, but if you want to use it in your own Application, you can.

```csharp
GameStartEvent.Subscribe(void Method(bool failed))
```
