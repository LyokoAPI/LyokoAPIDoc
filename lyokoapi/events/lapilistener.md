---
description: >-
  The LAPIListener class is a helper class to easily work with events and to
  prevent unnecessary boilerplate code.
---

# LAPIListener

To make a LAPIListener, just extend your listener class like so:

```csharp
public class MyExampleListener : LAPIListener
```

## Listening to events

To listen to events, you first need to enable the listener. In your main plugin class, or wherever you need the listener to be, write this:

```csharp
LAPIListener listener = new LAPIListener();
listener.StartListening();
```

Similarly, you can stop listening to events **\(which you may have to according to the** [**Rules**](https://github.com/LyokoAPI/LyokoAPIDoc/tree/fdb5e716f468c7556934771f257aae38e4ec78bc/docs/LyokoAPI/Events/LyokoPlugin/introduction.md)**\)**:

```csharp
listener.StopListening()
```

To listen to a specific event, override it's method:  


```csharp
public class MyExampleListener : LAPIListener
{
  public override void onLW_Death(LyokoWarrior warrior)
  {
    //some code that runs when a LW dies
  }
}
```

The details about each event can be found in the rest of the documentation.

You can find a list of events that the LAPIListener currently supports by checking out the class itself on github. For the master branch, this is: [https://github.com/LyokoAPI/LyokoAPI/blob/master/LyokoAPI/API/LAPIListener.cs](https://github.com/LyokoAPI/LyokoAPI/blob/master/LyokoAPI/API/LAPIListener.cs)

