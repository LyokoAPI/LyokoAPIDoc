#APIActivator
A person or entity that can activate and ITower

##Values
XANA, JEREMIE, HOPPER
NONE - the activator when the ITower is inactive.

##Parsing
If you want to parse a string to an Activator,
you can use LyokoParser.

The methods below can also be applied to a specific activator, like ``APIActivator.XANA.Parse()``, although that's pretty silly to do.

###ParseActivator
Accepts a string, returns an APIActivator
Throws a FormatException if the string is invalid.
```Java
APIActivator activator;
try{
  activator = LyokoParser.ParseActivator("XANA")
}catch (FormatException e) {
  LyokoLogger.Log(plugin.Name,e.Message); //will output something like 'Inalid activator: (activatorstring)'
}
```

###TryParseActivator
Accepts a string, returns a boolean if its a valid Activator. If true, stores it in a given variable.
```Java
APIActivator activator;
if (!LyokoParser.TryParseActivator("XANA", out activator)) {
  LyokoLogger.Log(plugin.Name,"Not a valid activator!")
}
```
