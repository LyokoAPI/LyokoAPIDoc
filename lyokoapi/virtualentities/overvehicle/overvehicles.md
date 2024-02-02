# Overvehicles

The Overvehicles class is a enum-ish class that provides the [Overvehicle ](overvehicle.md)object associated with a [OverVehicleName](overvehiclename.md)

## Getting an Overvehicle

You can get a Overvehicle either by a string name, a static name, or it's [OverVehicleName](overvehiclename.md) or by the [Lyokowarrior ](../lyokowarrior/lyokowarrior.md)that is riding it (either as driver or as passenger)

### By static name

You can get a specific OV like this:

```csharp
//check the HP of Overwing
int hp = Overvehicles.OVERWING
```

### By string name

If you have to work with a string, for example when you are using user input, you can get it like this:

```csharp
string name = "Overbike";
Overvehicle vehicle = Overvehicles.GetByName(name);
```

It will throw an `ArgumentException` if the OV does not exist.

### By Rider

You can also use a [Lyokowarrior  ](../lyokowarrior/lyokowarrior.md)to find an Overvehicle:

```csharp
//get the vehicle that Odd is riding
Overvehicle vehicle = Overvehicles.GetByWarrior(LyokoWarriors.ODD) 
```

This will return `null` if the warrior isn't riding a vehicle. You can check this with [LyokoWarrior.IsRidingVehicle()](../lyokowarrior/lyokowarrior.md#isridingvehicle)

### By LyokoWarriorName

You can also use [OverVehicleName](overvehiclename.md) to find an Overvehicle:

```csharp
Overvehicle vehicle = Overvehicles.GetByName(OverVehicleName.OVERWING)
```
