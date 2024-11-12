assignment 8
1. Const ensures that a created object is immutable, hence its state cannot be changed after creation. 

Advantages:
- Optimizes performance by making Flutter recognize certain objects to be pre-built and immutable, which allows Flutter to just reuse objects instead of creating new ones, hence avoiding unnecessary calculations and object allocations. Const keyword also instructs Dart VM to perform optimizations at compile time (faster object creation).
- Makes code easier to understand and since the objects cannot be changed after creation, it simplifies how data flows through our app to reduce risk of unexpected behavior and eases the debugging process.
- Reduces unnecessary widget creation and rebuilds.
- Easier testing and composing complex functionalities.

When to use:
- Immutable data objects: colors, configurations, data that shouldn't change.
- Pre-defined Values: API endpoints or static values
- Optimizing widget trees: reduces unnecessary widget creation

When NOT to use:
- Dynamic data: if an object's data needs to be modified after creation
- Network calls: objects fetching data from external sources


2. Columns arranges child widgets vertically (top to bottom), it is more suitable when content needs to be displayed in a single column (ex: list of options, form, vertical buttons)
Example:
Column(
  crossAxisAlignment: CrossAxisAlignment.start,
  children: [
    const Text(
      'Product Entry Form',
      style: TextStyle(fontSize: 24, fontWeight: FontWeight.bold),
    ),
    const SizedBox(height: 8),
    TextFormField(
      decoration: InputDecoration(
        labelText: 'Product Name',
        border: OutlineInputBorder(),
      ),
    ),
    const SizedBox(height: 8),
    TextFormField(
      decoration: InputDecoration(
        labelText: 'Description',
        border: OutlineInputBorder(),
      ),
    ),
    const SizedBox(height: 8),
    ElevatedButton(
      onPressed: () {},
      child: const Text('Save'),
    ),
  ],
)

Rows arranges child widgets horizontally (left to right), it is more suitable when content displays icons or buttons side-by-side.
Example:
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    InfoCard(title: 'NPM', content: npm),
    InfoCard(title: 'Name', content: name),
    InfoCard(title: 'Class', content: className),
  ],
),

3. The input elements used in this project so far is just TextFormField since the input we receive is just text for now. It is used to enter text in both Name and Description fields and used to input numeric values for Amount field. There are other common input elements in Flutter, examples include:
- DropdownButtonFormField: displays dropdown menu to select set value from list of options
- Checkbox: displays checkbox for Boolean values, used for options like Agrre to Terms, etc.
- Radio: allows user to select a single option from multiple choices
- Slider: allows user to select value from range by sliding thumb along a track, used to adjust values such as volume, brightness, etc.
- Switch: toggle switch for true/false values, often used for settings or preferences
- etc.

4. We can ensure consistency by defining it in the MaterialApp widget, the theme property accepts a ThemeData objects to set colors, text styles, button themes, etc. I also implemented a theme by using Theme.of(context) function.

5. I used a Navigator class to push and pop routes. I used Navigator.push to go to a new page and Navigator.pop to return to the previous page. For apps with a drawer or bottom navigation bar, the PageView widget or a state management solution can be used to maintain the state of each screen.

assignment 7
1. State of Widget: the information about the properties held by the objects at time of creation and can change when it is used.
Stateless Widget: Immutable widgets, appearance and properties do not change throughout the existence of the widget (cannot change state), ex: Icon, IconButton, Text
Stateful Widget: Widgets that change properties during runtime, they are dynamic, mutable and can change its appearance according to events triggered by user interaction or when it receives data, ex: Checkbox, Slider, Form

2. - MyHomePage: this is the main widget that displays InfoCard and ItemCard widgets on the home page
- InfoCard: displays NPM, Name, Class details
- ItemHomepage: this is a data model to store button information (name and icon) tht helps structure the ItemCard widgets
- ItemCard: displays clickable cards ("View Product List, "Add Product", "Logout")
- GridView: used to arrange ItemCard into 3 column layout

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
const: behaves like 'final', but 'const' makes the variable constant from compile-time only, so if we use it on an object, it will make the object's entire deep state fixed at compile-time and objects with this state are considered frozen and completely immutable.

5. First we generate a new project and run it to see that we have our page, then we reorganize it so that we can understnad our code easily. We reorganize it by moving class MyHomePage and class _MyHomePageState from main.dart to menu.dart. Finally, we create 5 widgets. This is done ny changing the app theme color, then, changing the widget page menu to stateless. Next, we create card with NPM, Name and Class, then we create the buttons, finally, we integrate InfoCard and ItemCard using GridView.
