# Parameter Types

### What Are Parameter Types? <a id="what-are-parameter-types"></a>

These is how the framework handles your arguments.  
I'll start by showing examples:

```java
@Command("cmd")
public class CommandTest extends BaseCommand {

    @SubCommand("material")
    public void selectMaterial(final CommandSender sender, final Material material) {
        if (material == null) {
            // error message here
            return;
        }

        sender.sendMessage(material.getName());
    }

}
```

The class and method above would be the same as someone typing the following in game:  
`/cmd material DIAMOND_ORE`.  
The second parameter is of the type `enum`. It is automatically checked if the player selected a valid material and passes it to your command method.  
It is important to check for `NULL`, as if the value entered by the player doesn't exist, it'll return `NULL`.  
This is on purpose and it's for easily handling your errors instead of relying on unnecessary message registering.  
Currently **MF** supports diverse number of parameter types by default.

### Default Types <a id="default-types"></a>

* Short
* Integer
* Long
* Float
* Double
* String
* String\[\]
* Player
* Material
* Boolean
* boolean
* World

_Due to the resolver returning null for invalid entries for easy error handling it is **highly** recommended to use object instead of primitive types when handling numbers as int/double/etc **will give you an error**._

### Registering Parameter <a id="registering-parameter"></a>

Need a parameter that is not accepted? Simply register it!  
For this let's give an example let's register a `Entity` that we get by it's UUID.  
On our `onEnable` method we get our `CommandManager` to register it.  
We first need to get the`ParameterHandler`.

```java
commandManager.getParameterHandler().register(Entity.class, argument -> {
    // Gets the entity from the UUID
    final Entity entity = Bukkit.getEntity(UUID.fromString(String.valueOf(argument)));
    // Checks if the entity is null or not and returns only the argument used
    if (entity == null) return new TypeResult(argument);
    // Returns the entity found and the argument
    return new TypeResult(entity, argument);
});
```

`Entity.class` is the class type you want to register, the `argument` is the argument the player just typed, you can use it to check if it is what you want it to be.  
We then return a `TypeResult` bject, which has two constructors, one that will accept an object in our case the entity and the other is the argument, the second is just for the argument, meaning the first object is null. This is useful for later to handle errors as if the entity is null it doesn't exist. It allows you to both handle your errors in the command class and also to get the raw value of the command typed, making it possible for you to have case specific error messages in your command class.  
By registering a new parameter with the same `Class` as an existing one, you can override it.

### Don't wish to use it? <a id="don-t-wish-to-use-it"></a>

If you don't want to use parameters like this and prefer to have more freedom then simply use `String[]` as your second parameter.  
This would be the most basic command handling, where you can handle everything by yourself.

```java
@SubCommand("subcommand")
public void subCommand(final CommandSender sender, final String[] args) {
    // Handle the arguments yourself here
}
```

