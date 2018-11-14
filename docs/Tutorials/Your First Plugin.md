#Creating the plugin project
In order to make a plugin, <br>
create a new class library in your IDE (this should be easy to figure out using the GUI)<br>
The target framework must be compatible with .NET Framwork 3.5 (this is compatible with Unity)<br>
(example code can be found below)<br>

Once you compile the project, you'll find it's dll file in a directory like bin/debug/
This is the file you can drop in the Plugins folder of the Application.

#Understanding class libraries
LyokoAPI comes in the form of a class library. <br>
A class library is essentially a bunch of code that doesn't execute on it's own.<br>
Thus, it can't be used by itself. <br>
For C#, a library is compiled into a .dll file.<br>
*Fun fact: Windows uses dll's as well for its own use!*<br>
*In theory, you can use the dll's in other .NET languages like VB.NET*<br>
**Your Plugin must also be a class library**

##Referencing a class library
Adding a library (like LAPI) to your project is called referencing.<br>
[Referencing in Visual Studio](https://www.webucator.com/how-to/how-add-references-your-visual-studio-project.cfm) (the 'browse' section)<br>
[Referencing in Unity](https://answers.unity.com/questions/458300/how-to-use-a-external-dll.html)

We recommend using the Early Access Program of [JetBrains' Rider](https://www.jetbrains.com/rider/eap/).<br>
It's a renewable trial (lasts about a month), so it's essentially free.

To add a reference in Rider:<br>
(Right click project) -> add reference -> add from.. -> select LyokoAPI.dll

#Writing your plugin
There are of course, many ways to write a plugin,<br>
but here is a 'template' that you can take inspiration from.
See [Plugin Introduction](../LyokoPlugin/introduction) for more in-depth info.

##Main class
Only ONE class per plugin should extend LyokoAPIPlugin.

```csharp
public class MyPlugin : LyokoAPIPlugin  //Extend the LyokoAPIPlugin class
{
  public override Name {get;} = "ExamplePlugin"; //set the name of the plugin
  public override Author {get;} = "Noob"; //set the author of the plugin

  protected override bool OnEnable()
  {
     MyListener.StartListening(); //Starting to listen to events in the OnEnable() is recommended
     return true; //nothing went wrong, so we return true to show the plugin has been enabled properly
  }

  protected override bool OnDisable()
  {
     MyListener.StartListening() //Definitely stop listening to events OnDisable(), since code will still be run if you dont.
     return true; //disabled succesfully, returning true.
  }
  /*
  * This method is run when a gamesession starts in the Application (if it has game sessions.)
  *
  */
  public override void OnGameStart(bool storyMode)
  {
    MyListener.StopListening() //if your listners somehow break immersion, do this.
  }

  public override void OnGameEnd(bool failed)
  {
    Sound sound; //fictional sound class, as an example
    if (failed) //if the player has lost the game
    {
      sound = Sounds.EPICFAIL;
      LyokoLogger.Log(Name, "Lol you failed you epic loser"); //this will appear in the log as "[ExamplePlugin] Lol you failed you epic loser"
    }else
    {
      sound = Sounds.YAAY;
    }
    SoundPlayer.PlaySound(sound);

    MyListener.StartListening() //start listening because we stopped in OnGameEnd
  }

}
```

##Listener class
You dont need a seperate Listener class, but it looks clean and it's what we usually use internally.

```csharp
public static class Listener
{
  private static bool _listening = false;
  /*
  * These variables are needed to unregister events later.
  * We dont really recommmend this in this situation
  */
  private static var onTowerdeactivation;
  private static var onXanaAwaken;
  private static var onHijack;

  public static void StartListening()
  {
    if(_listening)) { return;} //dont do anything if we're already listening

    TowerActivationEvent.Subscribe(OnTowerActivation); //Give the method name without '()'.
    XanaDefeatEvent.Subscribe(DoAThing); //the name of the method doesn't matter as long as the return value and parameters are the same

    TowerDeactivationEvent.Subscribe(tower => KeyboardRGB.ResetColor()) //single statement lambda with one parameter

    XanaAwakenEvent.Subscribe(() => SoundPlayer.PlaySound(Sounds.BeethovensFifth)) //single statement lambda with no parameters

    TowerHijackEvent.Subscribe((tower, oldactivator, newactivator) => //multi statement lambda with 3 parameters
    {
        SoundPlayer.PlaySound(Sounds.Thief);
        OnTowerActivation(tower); //you can re-use methods if you want, they're still methods.
    })
    _listening = true;
  }
  public static void StopListening()
  {
    if (!_listening) {return;} //dont stop listening if we've already stopped (unregistering events that haven't been registered is harmless though)
    TowerActivationEvent.Unsubcribe(OnTowerActivation);
    XanaDefeatEvent.Unsubcribe(DoAThing);

    /*
    * these unregister the listeners by using the delegate returned by Subscribe()
    */
    TowerDeactivationEvent.Unsubscribe(onTowerdeactivation);
    XanaAwakenEvent.Unsubscribe(onXanaAwaken);
    TowerHijackEvent.Unsubcribe(onHijack);

  }

  private static void OnTowerActivation(ITower tower)
  {
    Color color; //fictional color class
    switch(tower.Activator)
    {
      case APIActivator.XANA: color = Color.RED; break;
      case APIActivator.JEREMIE : color = Color.GREEN; break;
      case APIActivator.HOPPER : color = Color.WHITE; break;
    }
    KeyboardRGB.SetColor(color); //fictional KeyboardRGB class
  }

  private static void DoAThing()
  {
    LyokoLogger.Log("ExamplePlugin","I did a thing!");
  }




}
```
