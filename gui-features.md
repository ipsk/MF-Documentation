# GUI Features

After the basics of a GUI there is a lot more useful features you can use.

## Command features

The following are the common features in all GUIs.

### Fill item

Setting you fill item will fill the slots in your GUI that doesn't contain a GUI item.

```java
// Single fill item
gui.fill(new GuiItem(new ItemStack(Material.BLACK_STAINED_GLASS_PANE)));

// Multiple fill items
gui.fill(Arrays.asList(new GuiItem(new ItemStack(Material.BLACK_STAINED_GLASS_PANE)), new GuiItem(new ItemStack(Material.WHITE_STAINED_GLASS_PANE))));
```

Just like any other item these items can also have a click action, but they'll be the same for all the slots it is filled.

### Fill border

Just like the example above, but fills only the borders of the GUI.

### Fill top

Fills only the top of the GUI.

### Fill bottom

Fills only the bottom of the GUI.

### Set default click action

You can also set a default click action, which will be applied to every single slot in the GUI. For example if you call `event.setCancelled(true)` as your default action, you no longer need to cancel it for every single item.

```java
gui.setDefaultClickAction(event -> {
    // Handle your default action here
});
```

### Set close GUI action

This will display the action you set when ever the GUI is closed.  
The event passed down for this action is the `InventoryCloseEvent`.

```java
gui.setCloseGuiAction(event -> {
    // Handle your close action
});
```

### Set open GUI action

This will display the action you set when ever the GUI is open .  
The event passed down for this action is the `InventoryOpenEvent`.

```java
gui.setOpenGuiAction(event -> {
    // Handle your open action
});
```

### Slot actions

If you want to add a click action to a specif slot without needing to have to specify the item in the slot, you can simple use the `setSotAction`.  
It also supports both rows and columns and slots.

```java
// With slot
gui.addSlotAction(slot, event -> {
    // Handle your open action
});

// With rows and collumns
gui.addSlotAction(row, col, event -> {
    // Handle your open action
});
```

### Update

The `update` method will update the entire GUI except the title, due to how inventories work.

```java
gui.update();
```

### Update title

This will also update the title but you need to pass the new title down. However this method is not recommended if you're running it on a runnable as it can cause some TPS loss.

```java
gui.updateTitle("new title");
```

### Update Item

This is the preferable way of making updates in your GUI, for example an item that keeps refreshing, etc.  
This is recommended over the other ones as it'll simply change one item instead of the whole GUI.  
It also supports both rows and columns and slots.

```java
// Using slots
gui.updateItem(slot, new ItemStack(Material.STONE));

// Using rows and collumns
gui.updateItem(row, col, new ItemStack(Material.STONE));
```

### Item Builder

MF-GUI already comes with a built in ItemBuilder to make it easier for you to create custom items.

### XMaterials

The framework comes with XMaterials from the [**XSeries** ](https://github.com/CryptoMorin/XSeries)included for easier multi version support.

## Paginated GUI

Features only included in the `PaginatedGui`.

### Add Item

The add item is different on this GUI as it is the main source of populating the pages.

### Current page number

You can use `getCurrentPageNum()` to get the number of the current page.

### Get next page number

The method `getNextPageNum()`will return the number of the next page or `-1` if it is there is no next page.

### Get previous page number

The method `getPrevPageNum()`will return the number of the previous page or `-1` if it is there is no previous page.

### Next Page

The method `nextPage()` is used to go to the next page.

### Previous Page

The method `prevPage()` is used to go to the previous page.

