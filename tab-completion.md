# Tab Completion

To handle tab completions using **MF** you have three ways. With a method annotation, on a direct parameter annotation or using the `@CompleteFor` annotation.  
Examples:  
_Method_

```java
@SubCommand("test")
@Completion({"#players", "#range:1-20"})
public void tabExample(final CommandSender sender, final Player player, final Integer number) {
}
```

_Parameter_

```java
@SubCommand("test")
public void tabExample(final CommandSender sender, @Completion("#players") final Player player, @Completion("#range:1-20") final Integer number) {
}
```

On both examples, it'll complete the first argument with a list of online players and the second with numbers from `1` to `20`.

### Default Completions <a id="default-completions"></a>

By default MF will register the following completions:

* **\#players**
  * This will complete with a list of all online players.
* **\#empty**
  * This will complete with nothing, will be blank.
* **\#range**
  * Range can be used to generate a range of numbers, example `#range:20` will be from `1` to `20`, `#range:0-5` will be from `0` to `5`, doing just `#range` will default to `1` to `10`.
* **\#enum**
  * This will complete with a list of the enum values you have on your parameter, works with any enum.

### Registering Completion <a id="registering-completion"></a>

Since only the basics are registered by default, you'll probably want to register more, to do so, it's extremely similar to registering a new parameter.  
Based on the parameters we registered earlier, let's register a list of world names.

```java
commandManager.getCompletionHandler().register("#worlds", input -> {
    return Bukkit.getWorlds().stream().map(World::getName).collect(Collectors.toList());
});
```

The first parameter is a string with the completion ID you want, in this case `#worlds`, don't forget the `#`.  
By registering a new completion with the same ID as an existing one, you can override it.

### CompleteFor

CompleteFor would need to be on a separate method and linked to the sub command you want to tab complete for. This should mostly be used if you want to create very specific tab completions.   
**For example:** checking if the first argument is `X` if so, complete the second argument with `Sounds`, if first argument is `Y` complete the second argument with `Materials`.

```java
@CompleteFor("test")
public List<String> commandCompletion(final List<String> completionArguments) {
    // Handle the tab completion for the Sub Command "test" here.
    
    return new ArrayList<>();
}
```

### Hiding tab completion <a id="hiding-tab-completion-without-permissions"></a>

You can also set **MF** to hide tab completion for players that don't have permission to use the commands using the method `hideTabComplete`.

```java
commandManager.hideTabComplete(true);
```

Alternatively you can just make it by default on your `CommandManager` constructor on your `onEnable` method.

```java
CommandManager commandManager = new CommandManager(this, true);
```

