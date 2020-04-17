# Change Log

#### **v1.3**

* Commands can now be registered in the plugin.yml file without causing any problems.
* Tab completions will be "colored" when added automatically, for example: Adding a list containing \`&\` will make it be colored.

#### **v1.2.4**

* Fix problem where using parameter completions, the check was inverted.

#### **v1.2.2**

* Did an overhaul on the parameter types registering and handling to be cleaner and easier to understand. **Important** it no longer returns an Object array but an`TypeResult`object, this is for much easier handling and understanding, updated it [**here**](https://mf.mattstudios.me/parameter-types#registering-parameter).
* Added default support for `Boolean` ,`boolean` , and `World` types.
* Added `SyntaxError`exception that you can throw inside the command method which will trigger the Wrong Usage message.
* Changed handling of the methods so the errors caused by the command method are easier to read and find the problem, it'll no longer point it to the command handler but to the method itself.
* Fixed issue where wrong usage message wasn't being sent.
* Fixed issue where wrong usage message was being doubled while using the annotation with an ID.
* Removed the first argument from the list provided to the `CompleteFor` method which had the SubCommand name, now it'll only be the raw arguments the player is typing.
* Fixed problems with the \#range completion where it was causing errors.

#### **v1.1.3**

* Added option to register multiple commands in the same call.

#### **v1.1.2**

* Added `@Values` annotation.
* Fixed problem where command completion wasn't being registered correctly causing an error on startup.

#### **v1.1.1**

* Big code clean up.
* Fixed annotation typo.
* Removed unintentional debug messages.
* Better checks for the restricted usages.

#### **v1.1**

* Added `@CompleteFor` and `@WrongUsage`and it's usages.
* Removed `@MaxArgs` and `@MinArgs` due to being virtually unnecessary.
* Fixed problems with hide tab complete not working properly.
* Added option to default tab complete on the `CommandManager` constructor.
* Renamed artifact id to`matt-framework` because it looks better.
* Code clean up and some structural improvements.
* Compiling with Spigot`1.15.1`.

#### **v1.0.2**

* Commands are no longer case sensitive.
* Added `@Optional` parameter annotation, which allows you to create optional arguments.
* Added option to hide tab complete for commands players don't have permission for.
* Many bug fixes.

#### **v1.2.0-BETA**

* Changed from complex messages and throwing exceptions on parameters to simply returning `null`, to simplify error handling.
* Added `getArgument(String argumentName)` to `CommandBase` which allows you to retrieve the raw argument typed by the player for custom error messages.
* Better command handling which will make it faster.
* Removed default messages for specific errors like `arg.must.be.number`.
* Changed messages registration to no longer require the argument.

#### **v1.0.8-BETA**

* Added Tab completion to default commands.
* Fixed tab completion errors getting out of index.
* Fixed out of index errors for subcommands.
* Fixed sub command giving syntax errors in the presence of a default command with arguments.

#### **v1.0.5-BETA**

* Fixed `@Default` as it was broken by previous update.
* Made it easier to hide tab completion for later.

