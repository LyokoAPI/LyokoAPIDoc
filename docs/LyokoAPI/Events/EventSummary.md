#Events
The core of LAPI's workings' are is the usage of events.
These are messages that are typically sent by the Application, and processed by a Plugin.
Here's an oversight of how they work.

##Subscribing
The point of an event is that code is executed when it happens.
A method that waits for an event to happen, is usually called a Listener.
We will call adding a listener **Subscribing**.

A method that subscribes to an event must be of a certain format.
For example, a TowerEvent requires a Tower parameter.
The format of a method is called a **delegate** in C#<br>
*Hint: You can find all the delegetes on the pages that describe the events*

You can subscribe to an event with:
``SomEvent.Subscribe(method)``

In practice, you can use a method or a lambda.
for example:
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
As a dev, you might want to stop listening to an event.
For example, it's good practice to stop listening if your Plugin is disabled.

To unsubscribe from an event, you need to have it stored in a variable.
The easiest way to do this is:
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
*Note for pluginDevs: verify with the ApplicationDev wether or not you are allowed to call Events by yourself*

As an Application dev, you'll want to notify your plugins (or other parts of your application) of certain events.
LAPI is designed to make this simple.
Do remember that if you pass an object, like a Tower to an event, listening methods will be able to change that object. (Unless you set variables to be internal, which you should do anyways)

This is why we recommend you use LAPI's built-in classes to create objects based on your code (see ITower and APITower for more info)
That is, unless you want your Application's data accessible.

Calling an event is simple:
``SomeEvent.Call(//parameters)``

For example, you could do:
```csharp
TowerDeactivationEvent.Call(new APITower("Lyoko","ice",1));
```
You can find more examples on the specific event pages.

##Locking
As an ApplicationDev, you might not want Plugins to call events on their own. You can prevent this by locking specific events.<br>
To ensure the events can only be locked and unlocked by you, you must call:
```csharp
Events.SetMaster()
```
You can lock all events with:
```csharp
Events.LockAll()
```
Or specific ones with:
```csharp
SomeEvent.Lock()
```
Of course,
```csharp
Events.UnlockAll()
SomeEvent.Unlock()
```
Works as well.

*note: LockAll() is simply an override. It'll lock all events regardless of their Lock status.*<br>
*Similarly, UnlockAll() will not unlock Locked events.*
