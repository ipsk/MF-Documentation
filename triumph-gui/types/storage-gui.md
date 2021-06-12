---
description: >-
  GUI that does not clear it's items on close/open, any external non GuiItem
  added to it will stay. (it does not persist on server restart)
---

# Storage GUI

![](../../.gitbook/assets/ezgif-6-0f0b0eb384f3.gif)

### Creating a Persistent GUI

To create a persistent GUI all you need to do is:

```java
StorageGui gui = Gui.storage()
        .title(Component.text("GUI Title!"))
        .rows(6)
        .create();
```

Just like the normal [GUI](gui.md) the first parameter is the rows the GUI should have.

### Adding the item to the GUI

Differently to the normal [GUI](gui.md), the `addItem` method takes an `ItemStack` instead. Any `GuiItem` added will have actions applied to it, the persistent items are simple ItemStacks that have nothing associated to it.

