1. Can we nest the Scaffold widget? Why or Why not?

 Ans: We cannot nest Scaffold widget usually, there should be one Scaffold for each page (more precisely, for each Route/screen), and that we should not nest Scaffolds.
The Scaffold was designed to be the single top level container for a MaterialApp and it's typically not necessary to nest scaffolds. For example in a tabbed UI, where the bottomNavigationBar is a TabBar and the body is a TabBarView, we might be tempted to make each tab bar view a scaffold with a differently titled AppBar. It would be better to add a listener to the TabController that updates the AppBar.

2. How to reduce the rebuilding of the widget?

Ans: Easiest ways to avoid unwanted reBuilds that are caused usually by calling setState() in order to update only a specific Widget and not refreshing the whole page, is to cut that part of our code and wrap it as an independent Widget in another Stateful classs. 
 mounted property is useful when a method on our state calls setState() but it isn't clear when or how often that method will be called. Perhaps its being called in response to a stream updating. we can use if (mounted) {... to make sure the State exists before calling setState().
 
3. How can I access platform(iOS or Android) specific code from Flutter?

Ans:By using Method Channel. 
Flutter code, Client and the platform code and Host binds to a common Method Channel. Client sends message to the Host through the Method Channel. Host listens on the Method  Channel, receives the message and does the necessary functionality and finally, returns the result to the Client through Method Channel.

4. What is BuildContext? What is its importance?

BuildContext is a locator that is used to track each widget in a tree and locate them and their position in the tree. The BuildContext of each widget is passed to their build method. Build method returns the widget tree a widget renders. Each BuildContext is unique to a widget.

Coding Questions:
1. In the below code, list1 declared with var, list2 with final and list3 with const. What is the difference between these lists? Will the last two lines compile?

Ans: list1 declared with var so data type for list is List Of String data type cannot be changes values ca be changed, list2 with final so values can be detected at the runtime. list3 with const the values can be detected at complete time.  list2[2]='Dart' will be complied. But  const list3= list1; it will Not a constant expression.
 
2. Identify the problem in the following code block and correct it.
 
Method name should in lowerCamelCase. correct Name would be: longOperationMethod();
Class members, top-level definitions, variables, parameters, named parameters and named constructors should capitalize the first letter of each word except the first word, and use no separators.
3. What is the main difference between Mobx & Provider? Can we use both together? Write code to demonstrate it.
 
The provider package is an easy to use package which is basically a wrapper around the InheritedWidgets that makes it easier to use and manage. It provides a state management technique that is used for managing a piece of data around the app.
ChangeNotifierProvider<T extends ChangeNotifier> It listens to a ChangeNotifier extended by the model class, exposes it to its children and descendants, and rebuilds depends whenever notifyListeners is called.
ChangeNotifierProvider(
  create: (context) => DataModel(),
  child: ...
)
 
Finllay i dont have idea about Mobx.
