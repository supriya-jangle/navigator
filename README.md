tor and Route classes to handle routing.
Steps:
1)Define multiple screens (or routes).
2)Navigate between screens using Navigator.push or Navigator.pushNamed.
3)Use Navigator.pop to return to the previous screen.
code:-
import 'package:flutter/material.dart';
void main() => runApp(MyApp());
class MyApp extends StatelessWidget {
 @override
 Widget build(BuildContext context) {
 return MaterialApp(
 initialRoute: '/', // Default route
 routes: {
 '/': (context) => HomeScreen(),
 '/second': (context) => SecondScreen(),
 },
 );
 }
}
class HomeScreen extends StatelessWidget {
 @override
 Widget build(BuildContext context) {
 return Scaffold(
 appBar: AppBar(title: Text('Home Screen')),
 body: Center(
 child: ElevatedButton(
 onPressed: () {
 // Navigating to the SecondScreen using named route
 Navigator.pushNamed(context, '/second');
 },
 child: Text('Go to Second Screen'),
 ),
 ),
 );
 }
}
class SecondScreen extends StatelessWidget {
 @override
 Widget build(BuildContext context) {
 return Scaffold(
 appBar: AppBar(title: Text('Second Screen')),
 body: Center(
 child: ElevatedButton(
 onPressed: () {
 // Navigating back to the previous screen
 Navigator.pop(context);
 },
 child: Text('Back to Home Screen'),
 ),
 ),
 );
 }
}
