# Your First Plugin

## Creating the plugin project

In order to make a plugin,   
 create a new class library in your IDE \(this should be easy to figure out using the GUI\)  
 The target framework must be compatible with .NET Framwork 3.5 \(this is compatible with Unity\)  
 \(example code can be found below\)  


Once you compile the project, you'll find it's dll file in a directory like bin/debug/ This is the file you can drop in the Plugins folder of the Application.

## Understanding class libraries

LyokoAPI comes in the form of a class library.   
 A class library is essentially a bunch of code that doesn't execute on it's own.  
 Thus, it can't be used by itself.   
 For C\#, a library is compiled into a .dll file.  
 _Fun fact: Windows uses dll's as well for its own use!_  
 _In theory, you can use the dll's in other .NET languages like VB.NET_  
 **Your Plugin must also be a class library**

## Choosing an IDE

We recommend Jetbrains' Rider. It's free if you have a student email, and once in a while an [Early Access Proram](https://www.jetbrains.com/rider/eap/) is available, which is also free.

## Adding LAPI to your project

{% tabs %}
{% tab title="Nuget" %}
### Adding the Nuget package

LAPI V2 and higher comes in a nuget package, found here: [https://www.nuget.org/packages/LyokoAPI/](https://www.nuget.org/packages/LyokoAPI/)   
 A nuget package insures that you can easily update LAPI and that all it's required components, like YamlDotNet, are also installed automatically

The method of adding a nuget package depends on your IDE. Here are some links to help you: [Rider](https://www.jetbrains.com/help/rider/Using_NuGet.html#finding)  
[Visual studio](https://dzone.com/articles/install-nuget-packages-in-visual-studio)
{% endtab %}

{% tab title="Manual" %}
### OBSOLETE: Referencing a class library

{% hint style="danger" %}
#### this approach is OBSOLETE since LAPI V2.0.0. Use the NUGET PACKAGE method instead
{% endhint %}

#### this approach is OBSOLTE since LAPI V2.0.0. Use the NUGET PACKAGE method instead

 Adding a library \(like LAPI\) to your project is called referencing.  
 referencing in Visual studio: https://www.webucator.com/how-to/how-add-references-your-visual-studio-project.cfm \(the 'browse' section\)  
 Referencing in Unity: https://answers.unity.com/questions/458300/how-to-use-a-external-dll.html We recommend using the Early Access Program of \[JetBrains' Rider\]\(https://www.jetbrains.com/rider/eap/\).  
 It's a renewable trial \(lasts about a month\), so it's essentially free. To add a reference in Rider:  
 \(Right click project\) -&gt; add reference -&gt; add from.. -&gt; select LyokoAPI.dll
{% endtab %}
{% endtabs %}

## Writing your plugin

There are of course, many ways to write a plugin,  
 but here is a 'template' that you can take inspiration from. See [Plugin Introduction](https://github.com/LyokoAPI/LyokoAPIDoc/tree/fdb5e716f468c7556934771f257aae38e4ec78bc/docs/LyokoPlugin/introduction/README.md) for more in-depth info on the rules of writing a good plugin.

### Main class

Only ONE class per plugin should extend LyokoAPIPlugin.

{% tabs %}
{% tab title="Main Class" %}
{% code title="ExamplePlugin.cs" %}
```csharp
public class ExamplePlugin : LyokoAPIPlugin
    {
        public override string Name { get; } = "ExamplePlugin"; //set the name of the plugin

        public override string Author { get; } = "Noob"; //set the author of the plugin
        
        //ATTENTION! this property is set to the AssemblyVersion in AssemblyInfo.cs by default. Please set the version there.
        //public override LVersion Version { get; } = "V1.0.1"; //semantic versioning is preferred. the format is X.X.Y.Y where X and Y are whole numbers and X is mandatory.

        public override List<LVersion> CompatibleLAPIVersions { get; } =
            new List<LVersion>() {"2.0.0", "2.0.1"}; //A list of LAPI versions this plugin should be compatible with.
        private LAPIListener MyListener = new MyListener();
        protected override bool OnEnable()
        {
            MyListener.StartListening(); //Starting to listen to events in the OnEnable() is recommended
            return true; //nothing went wrong, so we return true to show the plugin has been enabled properly
        }

        protected override bool OnDisable()
        {
            MyListener.StartListening(); //Definitely stop listening to events OnDisable(), since code will still be run if you dont.
            return true; //disabled succesfully, returning true.
        }

        /*
        * This method is run when a gamesession starts in the Application (if it has game sessions.)
        *
        */
        public override void OnGameStart(bool storyMode)
        {
            if (storyMode)
            {
                MyListener.StopListening(); //disabling the listener in order to prevent 'cheating' (wether or not you should do this depends on your plugin.
            }
        }

        public override void OnGameEnd(bool failed)
        {
            if (failed) //if the player has lost the game
            {
                LyokoLogger.Log(Name, "Lol you failed you epic loser"); //this will appear in the log as "[ExamplePlugin] Lol you failed you epic loser"
            }

            MyListener.StartListening(); //start listening because we might have stopped in OnGameEnd
        }

        /*
          this method runs when the player leaves the supercomputerinterface/laptop/whatever
        */
        public override void OnInterfaceExit()
        {
            MyListener.StopListening(); //Jeremie cant know about xanafication if he's not at his computer, so it would be cheating to listen to these events
        }

        public override void OnInterfaceEnter()
        {
            MyListener.StartListening(); //Turn it on because we turned it off in OnInterfacExit()
        }
    }
```
{% endcode %}
{% endtab %}

{% tab title="Listener Class" %}
{% code title="MyListener.cs" %}
```csharp
public class MyListener : LAPIListener
    {
        public override void onLW_Xanafication(LyokoWarrior warrior)
        {
            SystemSounds.Exclamation.Play();
            LyokoLogger.Log("ExamplePlugin",$"{warrior.WarriorName} was xanafied!");
        }

        public override void onLW_Dexanafication(LyokoWarrior warrior)
        {
            LyokoLogger.Log("ExamplePlugin",$"{warrior.WarriorName} is no longer xanafied.");
        }
    }
```
{% endcode %}
{% endtab %}
{% endtabs %}



