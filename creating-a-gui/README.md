# Creating a GUI

To create a GUI all you need to do is:

```java
// Main constructor
Gui gui = new Gui(plugin, 3, "Gui Title");

// Alternative
Gui gui = new Gui(plugin, "Gui Title");
```

It always requires your plugin's instance and a title. The second parameter is how many rows the GUI should have. If nothing is specified it'll default to `1`.

### Paginated GUI

If you want your GUI to have pagination you'll need the `PaginatedGui`.

```java
// Constructor
PaginatedGui gui = new PaginatedGui(plugin, rows, pageSize, "Gui Title");
```

The Page Size will define how big the GUI page can be, for example if you're going to use the bottom row for your navigation and you want a 6 rows GUI, the page size should be 45. To populate the GUI you'll need to use the method `addItem()` which will fill the GUI with the items you want.

### Persistent Gui

This GUI type will keep it's data whenever you open, it's used for having a storage GUI that contains static items as well.

```java
// Constructor
PersistentGui gui = new PersistentGui(plugin, rows, "Gui Title");
```

Just like the paginated GUI, this one comes with a different `addItem()` method which will add it to the inventory and return left overs in case the inventory is full.

### Creating a GUI item

Each item added to the GUI need to be a `GuiItem`.

```java
// Item without action
GuiItem guiItem = new GuiItem(new ItemStack(Material.STONE));

// Item with action
GuiItem guiItem = new GuiItem(new ItemStack(Material.STONE), event -> {
    // Handle your click action here
});
```

Each GUI item needs an item stack, you may want to add a click action or not.  
The action for an item is simply the `InventoryClickEvent` so handle it like you would be doing your own listener.  


### Adding item

Now that we have our `GuiItem`, we can easily add it to the GUI.

```java
// Using a slot number from 0 to 53
gui.setItem(slot, guiItem);

// Using rows and collumns
gui.setItem(row, col, guiItem);

// Using add item to add to next free slot
gui.addItem(guiItem);
```

You have the option to set it the way you want, for example the slot `0` is the `row 1, col 1`.

### Opening the GUI

To open the GUI to the player you just need to call the method `open`.

```java
gui.open(player);
```



