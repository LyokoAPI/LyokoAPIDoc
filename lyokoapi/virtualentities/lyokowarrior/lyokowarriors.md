# LyokoWarriors

## Lyokowarriors

The LyokoWarriors class is a enum-ish class that provides the [Lyokowarrior](lyokowarrior.md) object associated with a [LyokoWarriorName](lyokowarriorname.md).

## Getting a LyokoWarrior

You can get a LyokoWarrior either by a string name, a static name, or it's [LyokoWarriorName](https://github.com/LyokoAPI/LyokoAPIDoc/tree/a5b2e71d661b5e232a313d2e947906767206bc6f/docs/LyokoAPI/VirtualEntities/LyokoWarrior/LyokowarriorName.md)

### By string name

If you have to work with a string, for example when you are using user input, you can get it like this:

```csharp
string name = "ODD";
Lyokowarrior warrior = LyokoWarriors.GetByName(name);
```

It will throw an `ArgumentException` if the warrior does not exist.

### By static name

You can get a specific LW like this:

```csharp
//check the HP of William
int hp = Lyokowarriors.WILLIAM.HP
```

### By LyokoWarriorName

You can also use [LyokoWarriorName](lyokowarriorname.md) to find a Lyokowarrior:

```csharp
LyokoWarrior warrior = LyokoWarriors.GetByName(LyokoWarriorName.ODD)
```

