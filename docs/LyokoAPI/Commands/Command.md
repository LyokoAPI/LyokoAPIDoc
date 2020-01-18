# Command
The Command class implements [ICommand](ICommand.md).
It tries to offer an easy to use template for Plugin Developers and Application Developers and is meant to work with the [CommandListener](CommandListener.md)

# Members
Command Inherits the following members from [ICommand](ICommand.md):
* [Name](ICommand.md#Name)
* [DisplayName](ICommand.md#DisplayName) 

*note: DisplayName defaults to Name in this implementation*

## MinArgs
This int defines the minimum ammount of arguments that have to be passed. 
If there are less arguments than this number, the Command will throw a [CommandException](CommandException.md)

Defaults to 0

## MaxArgs
This int defines the maximum ammount of arguments that can be passed.
If there are more arguments than this number, the Command will throw a [CommandException](CommandException.md)

Defaults to ``Int32.MaxValue``

# Abstract methods
These methods have to be implemented when you extend this class.
