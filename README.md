1. Can we nest the Scaffold widget? Why or Why not?
 Ans: We cannot nest Scaffold widget usually, there should be one Scaffold for each page (more precisely, for each Route/screen), and that we should not nest Scaffolds.
The Scaffold was designed to be the single top level container for a MaterialApp and it's typically not necessary to nest scaffolds. For example in a tabbed UI, where the bottomNavigationBar is a TabBar and the body is a TabBarView, we might be tempted to make each tab bar view a scaffold with a differently titled AppBar. It would be better to add a listener to the TabController that updates the AppBar.

2. How to reduce the rebuilding of the widget?
 Easiest ways to avoid unwanted reBuilds that are caused usually by calling setState() in order to update only a specific Widget and not refreshing the whole page, is to cut that part of our code and wrap it as an independent Widget in another Stateful classs. 
 mounted property is useful when a method on our state calls setState() but it isn't clear when or how often that method will be called. Perhaps its being called in response to a stream updating. we can use if (mounted) {... to make sure the State exists before calling setState().
 
3. How can I access platform(iOS or Android) specific code from Flutter?
By using Method Channel. 
Flutter code, Client and the platform code and Host binds to a common Method Channel. Client sends message to the Host through the Method Channel. Host listens on the Method  Channel, receives the message and does the necessary functionality and finally, returns the result to the Client through Method Channel.
4. What is BuildContext? What is its importance?
