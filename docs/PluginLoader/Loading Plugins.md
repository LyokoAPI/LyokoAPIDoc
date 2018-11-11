#Creating the loader
*Note: this is intended for application developers.*<br>
To use the LyokoPluginLoader, <br>
you need to add the LyokoPluginLoader.dll and LyokoAPI.dll to your project.

You can create the loader with:
```csharp
PluginLoader = new PluginLoader(string path);
```
Where the path is the folder where you expect users to place Plugins.

##How the loading works
The plugin .dll's placed in the plugin folder will be looped over,
and if they extend [LyokoPlugin](../LyokoPlugin/introduction.md),
they will be loaded and enabled.

###LoggerPlugin
If a plugin is called is "LoggerPlugin", it'll be loaded before all others.

###Loading issues
If there's an issue loading or enabling the plugins, it'll be logged (assuming someone is listening)

##Methods

###DisableAll()
Calling this method will disable all plugins.
*note: there's no guarantee that a plugin will actually be disabled.*<br>
###EnableAll()
Calling this method will enable all plugins.
*note: there's no guarantee that a plugin will actually be enabled.* <br>

##Properties:
Plugins - A List of Plugins that are known.<br>
*Note: these can be both enabled and disabled.*
