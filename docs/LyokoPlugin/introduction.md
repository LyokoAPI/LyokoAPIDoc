#LyokoPlugin Introduction
Welcome plugin developer.

In this introduction we'll go over some rules we need to call a plugin LAPI-Compliant.
If you think your plugin conforms to all these rules, you can apply to get verified and appear on our list!

#Creating your Plugin
To create your plugin, you will need the LyokoAPI.dll and reference to it in your project.
How to do this depends on your IDE, but a short google search will help you.

You must declare one class that extends the LyokoPlugin class.
This will be recognized by the Application as your plugin.

##OnEnable()
This is the method that will 'start' your plugin.
In it, you should initialize all the variables you wish to use,
and register your listeners. (see [EventSummary](../LyokoAPI/Events/EventSummary.md) for more info)
If something went wrong during the start process, return false.
**If you return false in OnEnable(), the PluginLoader will try to run OnDisable(), please make sure that this works properly.**

##OnDisable()
This is the method that will 'stop' your plugin.
It wont, however, be 'deleted'.
**Make sure to disable all listeners in your onDisable()**
Just like with the OnEnable(), return false if something goes wrong.

##OnGameStart()
*note: this method assumes the Application has a concept of a game/game-session. If it doesn't, just leave it empty.*
**Do not throw an UnImplementedException**
This method is called when a game session starts.
It also passes a boolean StoryMode, that tells you wether or not the session is in a story mode or similar. It's intended to prevent 'cheating' or otherwise breaking immersion. Please disable your plugin if it could break the story somehow, using ``this.Disable()``

##OnGameEnd()
*note: this also assumes the existence of game-sessions, see above*
This method is called when a game session ends.
It also passes a boolean that tells you wether or not the user lost the game.
This method is particularly useful if you disabled your game because of Story Mode (see above).

#Debugging your Plugin
If you want to log something for debug purposes, or for error handling,
you can use LyokoLogger.
It works much like an event.

You can log something by calling
```Java
LyokoLogger.Log("YourpluginName","yourmessage");
```
It will appear in the log as "[PluginName] message"
You can find a plugin that logs these messages to a commandConsole window in the plugin list.

However, if you want to make your own logging plugin, you can do so by subscribe to it with ``LyokoLogger.Subscribe(method)``, it takes a ``void Method(string message)``. See  [EventSummary](../LyokoAPI/Events/EventSummary.md) for more info.
