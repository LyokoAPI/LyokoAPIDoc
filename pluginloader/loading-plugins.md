# Creating the loader

_Note: this is intended for application developers._\
&#x20;To use the LyokoPluginLoader, \
&#x20;you need to add the LyokoPluginLoader.dll and LyokoAPI.dll to your project.

You can create the loader with:

```csharp
PluginLoader = new PluginLoader(string path);
```

Where the path is the folder where you expect users to place Plugins.

## How the loading works

The plugin .dll's placed in the plugin folder will be looped over, and if they extend [LyokoPlugin](../lyokoplugin/introduction.md), they will be loaded and enabled.

### LoggerPlugin

If a plugin is called is "LoggerPlugin", it'll be loaded before all others.

### Loading issues

If there's an issue loading or enabling the plugins, it'll be logged (assuming someone is listening)

## Methods

### DisableAll()

Calling this method will disable all plugins. _note: there's no guarantee that a plugin will actually be disabled._\


### EnableAll()

Calling this method will enable all plugins. _note: there's no guarantee that a plugin will actually be enabled._ \


## Properties

Plugins - A List of Plugins that are known.\
&#x20;_Note: these can be both enabled and disabled._
