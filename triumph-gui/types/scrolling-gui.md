---
description: >-
  Simple GUI that allows you to scroll on a Paginated GUI instead of going page
  by page.
---

# Scrolling GUI

![](../../.gitbook/assets/ezgif-6-be4759200973.gif)

### Creating a Scrolling GUI

To create a Scrolling G

```java
ScrollingGui gui = Gui.scrolling()
        .title(Component.text("GUI Title!"))
        .rows(6)
        .pageSize(45)
        .scrollType(ScrollType.HORIZONTAL) // Not needed, defauilts to VERTICAL.
        .create();
```



Just like the normal [GUI](gui.md) the first parameter is the rows the GUI should have. Like the [Paginated GUI](paginated-gui.md) the second parameter is to specify the page size, as in how big the page should be, in the example above it's 45 slots dedicated for the page.

Everything else about this GUI is exactly like the [Paginated](paginated-gui.md).

