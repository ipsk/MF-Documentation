# Updating to 3.0.0

I've been long wanting to rename my libs as I didn't like the previous name. With this update this lib will finally be renamed to `triumph-gui`, others will be done shortly too as I finish some rewrites.  
Due to the name change and also some much needed organization, some packages had to be renamed/moved, which means you'll have to reimport a few things.

\*\*\*\*[**Adventure**](https://github.com/KyoriPowered/adventure): A much needed update. Every `GUI` and `ItemBuilder` now supports using `Components` for title/name.

{% hint style="warning" %}
When using Adventure and using Paper \(1.16.5+\) you do not need to add anything else to your project as it's already provided by Paper. If you want to support both this and previous versions while still using Adventure, you'll need to shade it.

You can also use plain Strings to work on Spigot and old versions, but it's not recommended, so it has been deprecated.
{% endhint %}

**GUI Builders**: Added a convenient way to create GUIs using the builders, it also comes with a few action limiting options, like disabling all clicks, disabling drag, disabling item moving from one inventory to the other, etc. For more check the specific GUI page as it has been updated.  
You can now also disable certain actions by default, like `disableAllInteractions`, `disableItemPlace`, `disableItemSwap`, and `disableItemTake` \(Big thanks to [SecretX](https://github.com/SecretX33) for this\).

**Item Builder**: The item builder has changed to be divided by function, the current `ItemBuilder.of()` will provide all the basic functionalities needed for a common item, for Skulls you can now do `ItemBuilder.skull()` this has all the skull related methods that used to be present in the old \`ItemBuilder\` so make sure to change this in your code. More builders for different purposes to come!  
Many methods in the `ItemBuilder` have been renamed, for example `setName` became just `name`, etc.

**XMaterials**: I have come to the conclusion to remove it from the lib, it did not make sense to be part of the lib and was only used internally in one situation. You are free to use it independently now, this is better because you can update it and use it at your own will. You can find it [here](https://github.com/CryptoMorin/XSeries).

**Hopper GUI**: The hopper GUI does not trigger the click event due to an issue involving `InventoryHolder` being null, so I decided to temporarily remove it until I can find a better fix.

**PersistentGUI**: This GUI type was renamed to `StorageGui` as it makes more sense and it is more descriptive of what it does, the previous name gave the wrong impression that it would keep items after server restart, which it doesn't. Soon I'll be adding support for multiple page storage and easy serialization built in.

Lastly, thank you for using my lib! If you find any issue feel free to open an issue or report to me on my discord!

