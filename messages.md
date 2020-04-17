# Messages

By default **MF** will generate simple messages to handle a few possible errors that can occur.

### Customizing <a id="customizing"></a>

To customize the messages or add new ones, it is just as similar to registering a new parameter or completion.  
For an example let's register a message for an invalid world name.

```java
commandManager.getMessageHandler().register("cmd.no.console", sender -> {
    sender.sendMessage("Command can't be used in the console!");
});
```

You can add as many lines as you want in there.  
The `sender` is a `CommandSender`, which you use to send the message to.  
The message ID is unique so using an existing one you'll override it.

### Default Messages <a id="default-messages"></a>

The default message IDs you can override with your own are the following:  
_Used in the command handling errors_

* **cmd.no.permission**
* **cmd.no.console**
* **cmd.no.exists**
* **cmd.wrong.usage**

### **Wrong Usage**

For registering a message to be used on the `@WrongUsage` annotation make sure the `ID` starts with the symbol `#`.

