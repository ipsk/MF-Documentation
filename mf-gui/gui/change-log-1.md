# Change Log

#### v2.0.2

* GUIs no longer require a plugin instance.
* Item NBT now caches reflection, should improve performance.
* ItemBuilder's `glow` should work correctly when removing the glow.
* Added [ScrollingGUI](scrolling-gui.md).
* Fixed `updateTitle` bug where the title would not update correctly.
* Fixed updating issues causing concurrent modification exception when more than 1 player had the GUI open.
* Updated XMaterials.
* Refactored the ItemBuilder to be more idiomatic.
* Better GUI validation for slots, the exception will be more descriptive.
* Added `GuiTypes` which allow you to have different InventoryTypes, like Workbech, Hopper, etc.
* Added Material constructor to GuiItem.
* Fixed filler not being able to fill top and bottom correctly and not being able to use multiple filling at the same time.
* GUI will no longer open if the player is asleep, due to it not triggering the `InventoryClickEvent`.
* PaginatedGUI's `nextPage` and `prevPage` have been replaced with `next` and `previous`.

#### v1.2.8

* Added `setNbt` to the item builder.

#### v1.2.7

* Update page item \(ItemStack\) now applies NBT like it should.
* Page size is no longer required, it'll be dynamically adjusted based on the empty spaces of the inventory.

#### v1.2.6

* Update item \(ItemStack\) now applies NBT like it used to.
* Changed paginated GUI to no longer need to reopen on page change \(should boost performance slightly\).
* Added null validation for the GUI Items.

#### v1.2.4

* Paginated GUI fix.
* NextPage and PrevPage methods now return a boolean.
* Get next page number no longer returns -1 if page doesn't exist, instead returns the current page number.
* Item Glow on ItemBuilder now requires a boolean.
* Added getPageItems, getCurrentPageItems and updatePageItem.

#### v1.1.5

* Added setLore method with List instead of varargs.

#### v1.1.4

* Add item fix for paginated GUI.
* Fixed fill border bug with max size GUI.

#### v1.1.1

* Restructured the GUIs and separated them in different ones with `GuiBase`as the main class.
* Added PaginatedGui - Thanks [**Gaby**](https://github.com/iGabyTM).
* Added PersistentGui.
* Added XMaterials for better version support.
* Changed ItemBuilder's skull method to use XMaterials and Mojang's methods.
* Added auto update to the GUI - Thanks [**Harolds**](https://github.com/harry0198)**.**
* Added close method to the GUI.
* Made methods to ensure GUI items can't be removed from the GUI.

#### v1.0.3

* Fixed problems cause by previous update.
* Replaced player skull by texture from the `ItemBuilder` to use reflection instead of NMS methods.

#### v1.0

* Finally released.
* Changed `setFillItem` to `fill`.
* Added `fillBorder`, `fillTop`, `fillBottom` and filling with multiple items, special thanks to [**Harolds**](https://github.com/harry0198)**.**

#### v1.1.0-BETA

* Small changes and code clean up.

#### **v1.0.2-BETA**

* First beta version.
* Added all the main features.

