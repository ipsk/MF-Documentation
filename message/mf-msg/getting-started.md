# Getting started

### Message

To get started first you need to create a `Message`.

```java
final Message message = Message.create();
```

This will be the base of every message you parse.

### Format Options

You can also specify some Format options to he message creator, this allows you to control how the message will be parsed.

The base of the format options is the `FormatOptions` builder:

```java
FormatOptions.builder();
```

With it you can disable some formats:

```java
final FormatOptions formatOptions = FormatOptions.builder().without(Format.BOLD);
```

In this example BOLD format will be disabled, it'll not parse the bold portion of the message.

You can also set a default color to be used in the messages:

```java
final FormatOptions formatOptions = FormatOptions.builder().defaultColor(new FlatColor("#38ef7d"));
```

Available color types are

* **FlatColor** - Takes in a String with a color, can be hex or just the name, for example: `FlatColor("red");`
* **Gradient** - Takes in two `Color` objects.
* **Rainbow** - Takes two values, a saturation level and a brightness level.

Finally you can pass the format options to the message creator:

```java
final Message message = Message.create(formatOptions);
```

### Parsing

Finally all it's left is parsing the message:

```java
final MessageComponent component = message.parse("**Hello** __everyone__!");
```

The `MessageComponent` holds the parsed values that you can be used for anything you want.

```java
// Sends JSON message
component.sendMessage(player);

component.sendActionBar(player, fadeIn, stay, fadeOut);
component.sendSubTitle(player, fadeIn, stay, fadeOut);
component.sendTitle(player, fadeIn, stay, fadeOut);

// Parsed String to use in items, etc
final String parsed = component.toString();
// Raw JSON String
final String json = component.toJson();
```

