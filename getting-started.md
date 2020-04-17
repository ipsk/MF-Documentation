# Getting started

### Command Manager <a id="command-manager"></a>

The command manager is responsible for doing almost everything in the framework, from registering commands to customizing messages.  
To start, first add it to your `onEnable` method.

```java
CommandManager commandManager = new CommandManager(yourPlugin);
```

### Creating Commands <a id="creating-commands"></a>

Now you have to create your first command class.  
Let's call it `CommandTest` for an example.  
Every command class must extend **CommandBase**.

```java
@Command("commandtest")
public class CommandTest extends CommandBase {
    //..
}
```

Inside this class we can add our commands and subcommands.  
First let's do the equivalent to `/commandtest` simply to send a message saying `Hello!`.

```java
@Default
public void defaultCommand(final CommandSender commandSender) {
    commandSender.sendMessage("Hello!");
}
```

Done! That simple.  
Now to add a subcommand called `test` that'll send a message saying `Test!`.  


```java
@SubCommand("test")
public void testSubCommand(final CommandSender commandSender) {
    commandSender.sendMessage("Test!");
}
```

The first parameter will dictate if the command can be executed by the console and player or just the player. If the first parameter is `Player player` instead of `CommandSender sender` it'll automatically make a player only command!

### Registering Commands <a id="registering-commands"></a>

To register the commands we just created we simply go back to the `onEnable` method and add the following.

```java
// Registering one command
commandManager.register(new CommandTest());

// Registering multiple
commandManager.register(new Command1(), new Command2(), new Command3(), ..);
```

That's all for the basic commands, for the more advanced ones you can just keep reading!

