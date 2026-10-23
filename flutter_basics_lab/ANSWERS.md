# GITHUB REPOSITORY
REPOSITORY LINK: https://github.com/ceeeeji/flutter_basics_lab


# ANSWERS

## Activity 2 Debug Console

build() called: 4 glasses
build() called: 5 glasses
build() called: 6 glasses

## Activity Observations

### Activity 2
When I moved `_glasses++` outside `setState()`, the screen did not update properly because Flutter was not told to rebuild the widget.

### Activity 3
When I removed `Expanded` from one `StatBox`, the boxes no longer shared the width equally.

### Activity 5
I changed the ElevatedButton corner radius from 8 to 20. The button became more rounded.

## Review Questions

# 1. What is the difference between a StatelessWidget and a StatefulWidget? Give one example of each from this lab.

A `StatelessWidget` is used when the information on the screen does not need to change while the app is running. A `StatefulWidget` is used when some data can change and the screen needs to update.

An example of a `StatelessWidget` is the `ProfileCard` from Activity 1. An example of a `StatefulWidget` is the `WaterTrackerPage` from Activity 2.

# 2. Why is a StatefulWidget written as two classes? What does each class do?

A `StatefulWidget` uses two classes because the widget itself and its changing data have separate jobs. The first class creates the State object. The second class stores the data that can change and contains the `build()` method that updates the screen.

For example, in Activity 2, `WaterTrackerPage` creates `_WaterTrackerPageState`, while `_WaterTrackerPageState` stores the number of glasses and handles the changes.

# 3. In Activity 2, what happened when you changed `_glasses` outside `setState()`? Why?

When `_glasses` was changed outside `setState()`, the screen did not properly update when the value changed. This is because `setState()` tells Flutter that the data has changed and that the widget needs to be rebuilt.

Without using `setState()` correctly, Flutter does not know that it needs to redraw the screen.

# 4. Looking at the Debug Console in Activity 2, when is `build()` called?

The `build()` method is called when the widget is first displayed and whenever `setState()` causes the widget to rebuild.

In Activity 2, I saw a new `build() called` message in the Debug Console every time the number of glasses changed.

# 5. Explain the main axis and the cross axis of a Row and of a Column.

For a `Row`, the main axis is horizontal because its children are placed from left to right. Its cross axis is vertical.

For a `Column`, the main axis is vertical because its children are placed from top to bottom. Its cross axis is horizontal.

# 6. In Activity 3, what happened when you removed Expanded from a StatBox? What does Expanded do?

When I removed `Expanded` from one `StatBox`, that box no longer shared the available width equally with the other boxes. Its size was based more on its own content, while the other boxes still used the remaining space.

`Expanded` makes widgets share the available space inside a `Row` or `Column`. In Activity 3, it made all four StatBoxes have equal widths.

# 7. Why do we use GridView.builder for the menu instead of a Column with many children?

`GridView.builder` is useful because it arranges the menu items into a grid and builds items as they are needed. This works better for a menu with many items and also allows the menu to scroll.

A `Column` would simply place all the items from top to bottom and would not be as suitable for a large, scrollable grid.

# 8. How do Stack and Positioned create the Best seller badge in Activity 4?

`Stack` allows widgets to be placed on top of each other. The menu card is placed normally, while the Best seller badge is added on top of it.

`Positioned` controls where the badge appears inside the Stack. In Activity 4, it places the badge near the top-left corner of the menu card.

# 9. What is the difference between customizing with ThemeData and with a style on one widget? Give one example of each from Activity 5.

`ThemeData` is used to customize the appearance of several widgets or the whole app. A style placed directly on one widget only changes that specific widget.

In Activity 5, `ThemeData` is used to set things such as the app colors, brightness, AppBar style, text style, and ElevatedButton style.

An example of styling one widget directly is using properties such as the color or appearance of a specific icon, text, or widget instead of changing the entire theme.

# 10. When you flip the dark-mode switch in Activity 5, which widget holds the state, and how does the change reach MaterialApp?

The dark-mode state is stored in `_ThemeDemoAppState` using the `_isDark` variable.

When the switch is changed, `SettingsPage` calls the `onDarkChanged` callback. This calls `_setDark()`, which changes `_isDark` inside `setState()`.

Flutter then rebuilds `ThemeDemoApp`, and `MaterialApp` uses `_isDark` to choose between `ThemeMode.dark` and `ThemeMode.light`.

