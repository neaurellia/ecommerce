assignment 7
1. State of Widget: the information about the properties held by the objects at time of creation and can change when it is used.
Stateless Widget: Immutable widgets, appearance and properties do not change throughout the existence of the widget (cannot change state), ex: Icon, IconButton, Text
Stateful Widget: Widgets that change properties during runtime, they are dynamic, mutable and can change its appearance according to events triggered by user interaction or when it receives data, ex: Checkbox, Slider, Form

2. 

3. setState() in Flutter is used to:
- Update the UI with New Values: It re-renders parts of the widget tree with updated data, useful for making the app responsive to changes.
- Trigger Stateful Changes (counters, input fields, or dynamically loaded data)
- Respond to User Interactions: For instance, if a user toggles a setting, setState() is used to reflect that change immediately on the screen.
- Handle Async Operations: Often used after fetching data or other asynchronous tasks, where you want to update the UI once the data is ready.

setState() affects only the state variables within a stateful widget. When you call setState(), it:
- Takes a callback that contains updates to variables declared in the widget’s state class.
- Triggers a rebuild of the widget, ensuring only the parts of the UI that rely on the updated variables are redrawn.

4. Both 'const' and 'final' are used to keep the value of a variable static (once defined, its state cannot be changed), however,
final: used to hardcore the values of variable and cannot be altered in the future, no operations on these variables can change its value.
const: behaves like 'final', but 'const' makes the variable constant from compile-time only, so if we use it on an object, it will make the object's entire deep state fixed at compile-time and objects with this state are considered frozen and completely immutable.# ecommerce
