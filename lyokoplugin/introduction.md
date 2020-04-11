# introduction

## LyokoPlugin Introduction

Welcome, plugin developer.

In this introduction we'll go over some rules we need to call a plugin LAPI-Compliant.  
 If you think your plugin conforms to all these rules, you can apply to get verified and appear on our list!

## Creating your Plugin

To create your plugin, you will need the LyokoAPI nuget package and add to it in your project.  
 Your plugin must be a class library that is compatible with .NET Framework 4.5  
 How to do this depends on your IDE. We have a tutorial for Rider and Visual Studio [here](../tutorials/your-first-plugin.md#adding-lapi-to-your-project).

You must declare one class that extends the LyokoPlugin class.  
 This will be recognized by the Application as your plugin.

**see the** [**Tutorial** ](../tutorials/your-first-plugin.md)**for a good example**

## General rules

* A plugin must not be for any kind of cheating.
* It must be open source \(unless you can persuade us to make an exception\)
* It must also not harm, annoy or bother the user or cause interference with the Application.

## Mandatory Properties

These properties must be present in your LyokoAPIPlugin in order to be LAPI-Compliant:  


### Name 

This is the name for your plugin. Preferably as unique as you can manage.

### Author

The name of you, or you and your partners. Choose a name that can be found somewhere in order to contact you.

### Version

The version of this plugin. Use a versioning system that makes sense, like [this one](http://apr.apache.org/versioning.html).

{% hint style="warning" %}
The Version of the plugin is the AssemblyVersion in AssemblyInfo.cs by default. Please set it there.
{% endhint %}

### CompatibleLAPIVersions 

A list of LAPI versions that this plugin is supposed to be compatible with.

### OnEnable\(\)

This is the method that will 'start' your plugin.  
 In it, you should initialize all the variables you wish to use, and register your listeners.  
 \(see [LAPIListener ](../lyokoapi/events/lapilistener.md)for more info\) If something went wrong during the starting process, return false.

{% hint style="danger" %}
 **If you return false in OnEnable\(\), the PluginLoader will try to run OnDisable\(\), please make sure that this works properly.**
{% endhint %}

### OnDisable\(\)

This is the method that will 'stop' your plugin.  
 It wont, however, be 'deleted'.  
 **Just like with the OnEnable\(\), return false if something goes wrong.**

{% hint style="warning" %}
 **Make sure to disable all listeners in your onDisable\(\)**
{% endhint %}

### OnGameStart\(\)

{% hint style="info" %}
This method assumes the Application has a concept of a game/game-session. If it doesn't, just leave it empty.

**Do not throw an UnImplementedException.**
{% endhint %}

 This method is called when a game session starts.  
 It also passes a boolean StoryMode, that tells you whether or not the session is in a story mode or similar. It's intended to prevent 'cheating' or otherwise breaking immersion.   
 Please disable your plugin if it could break the story somehow, using `this.Disable()`.

### OnGameEnd\(\)

{% hint style="info" %}
This also assumes the existence of game-sessions, see above.
{% endhint %}

 This method is _c_alled when a game session ends.  
 It also passes a boolean that tells you wether or not the user lost the game.  
 This method is particularly useful if you disabled your game because of Story Mode \(see above\).

### OnInterfaceExit\(\)

{% hint style="info" %}
This method assumes the Application has a concept of a interface \(that is, a computer with access to lyoko\) which can be entered or exited.
{% endhint %}

This method is called when a user of the Application has left the interface, and thus can't see any information about Lyoko and such. \(Example: Free Roam in IFSCL\)  
 If a user is not supposed to receive information \(eg when a tower is activated\) at this time \(as in, when away from the interface\), you can use this method to disable information being displayed in your plugin. \(You need to provide this functionality yourself, this method just tells you when to\)

### OnInterfaceEnter\(\)

_**Note: same as above**_  
****This method is called when a user of the Application has entered the interface, thus can see information about Lyoko and such.  
 If you disabled certain information from showing because of the method explained above, this is what you can use to re-enable it \(again, you must provide this functionality yourself, this just tells you when\)

## Debugging your Plugin

If you want to log something for debug purposes, or for error handling, you can use LyokoLogger.  
 It works much like an event.

You can log something by calling

```csharp
LyokoLogger.Log("YourpluginName","yourmessage");
```

It will appear in the log as "\[PluginName\] message".  
 You can find a plugin that logs these messages to a Command Console window in the plugin list.

However, if you want to make your own logging plugin, you can do so by listening to it with [LAPIListener](../lyokoapi/events/lapilistener.md), or manually:  
 `LyokoLogger.Subscribe(method)`, it takes a `void Method(string message)`. 
