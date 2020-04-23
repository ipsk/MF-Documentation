# Change Log

#### v1.2.3

* Paginated GUI fix.
* NextPage and PrevPage methods now return a boolean.
* Get next page number no longer returns -1 if page doesn't exist, instead returns the current page number.
* Item Glow on ItemBuilder now requires a boolean.

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

