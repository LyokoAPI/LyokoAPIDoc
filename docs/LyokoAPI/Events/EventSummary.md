#Events
The core of LAPI's workings' is the usage of events.<br>
These are messages that are typically sent by the Application, and processed by a Plugin.<br>
Here's an oversight of how they work.<br>

##Subscribing
The point of an event is that code is executed when the event is called.<br>
A method that waits for an event to happen, is usually called a Listener.<br>
We will call adding a listener **Subscribing**.

A method that subscribes to an event must be of a certain format.<br>
For example, a TowerEvent requires a Tower parameter.<br>
The format of a method is called a **delegate** in C#.<br>
*Hint: You can find all the delegetes on the pages that describe the events.*

You can subscribe to an event with:<br>
``SomeEvent.Subscribe(method)``

In practice, you can use a method or a lambda.
For example:
```csharp
public Listener(){
  TowerActivationEvent.Subscribe(onTowerActivation);
}

public void onTowerActivation(ITower tower){
  Console.WriteLine("Tower {0} {1} activated!",tower.Sector.Name, Tower.Number);
}
```
Can also be written as:
```csharp
public Listener(){
  TowerActivationEvent.Subscribe(tower =>
  Console.WriteLine("Tower {0} {1}",tower.Sector.Name,tower.Number));
}

```
##Unsubcribing
As a dev, you might want to stop listening to an event.<br>
For example, it's good practice to stop listening if your Plugin is disabled.

To unsubscribe from an event, you need to have it stored in a variable.<br>
The easiest way to do this is:<br>
```csharp
var listener;
public void StartListening(){
  listener = SomeEvent.Subscribe(foo => foo.Bar());
}
public void StopListening(){
  SomeEvent.Unsubcribe(listener);
}

```



##Calling
As an ApplicationDev, you'll want to notify your plugins (or other parts of your application) of certain events.<br>
LAPI is designed to make this simple.<br>
Do remember that if you pass an object, like a Tower to an event, listening methods will be able to change that object. <br>
(Unless you set variables to be internal, which you should do anyways).

This is why we recommend you use LAPI's built-in classes to create objects based on your code.<br>
(see [ITower](./Interfaces/ITower) and [APITower](./VirtualStructures/APITower) for more info)<br>
That is, unless you want your Application's data accessible.

Calling an event is simple:
``SomeEvent.Call(/*parameters*/)``

For example, you could do:
```csharp
TowerDeactivationEvent.Call(new APITower("lyoko","ice",1));
```
You can find more examples on the specific event pages.
