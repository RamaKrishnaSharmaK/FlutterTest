 Can we nest the Scaffold widget? Why or Why not?
 Ans: We cannot nest Scaffold widget usually, there should be one Scaffold for each page (more precisely, for each Route/screen), and that we should not nest Scaffolds.
The Scaffold was designed to be the single top level container for a MaterialApp and it's typically not necessary to nest scaffolds. For example in a tabbed UI, where the bottomNavigationBar is a TabBar and the body is a TabBarView, we might be tempted to make each tab bar view a scaffold with a differently titled AppBar. It would be better to add a listener to the TabController that updates the AppBar.
 
 
 
2. How to reduce the rebuilding of the widget?
3. How can I access platform(iOS or Android) specific code from Flutter?
4. What is BuildContext? What is its importance?
