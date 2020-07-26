---
description: >-
  Simple GUI that allows you to scroll on a Paginated GUI instead of going page
  by page.
---

# Scrolling GUI

![](../../.gitbook/assets/ezgif-6-be4759200973.gif)

### Creating a Scrolling GUI

To create a Scrolling GUI all you need to do is:

```java
// Main constructor
ScrollingGui scrollingGui = new ScrollingGui(6, 45, 9, "GUI Title");

// Alternative
ScrollingGui scrollingGui = new ScrollingGui(6, "GUI Title");

// Horizontal scrolling instead of vertical
ScrollingGui scrollingGui = new ScrollingGui(6, 45, 5, "GUI Title", ScrollType.HORIZONTAL);
```

Just like the normal [GUI](gui.md) the first parameter is the rows the GUI should have. Like the [Paginated GUI](paginated-gui.md) the second parameter is to specify the page size, as in how big the page should be, in the example above it's 45 slots dedicated for the page, the third parameter tells the lib how many items at a time it should scroll, the example above uses `9`, if nothing is set the lib will calculate the page size and the scroll size when opening.

Everything else about this GUI is exactly like the [Paginated](paginated-gui.md).

