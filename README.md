import 'package:flutter/material.dart';

void main() => runApp(PathHelperApp());

class PathHelperApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Path Helper',
      home: HomePage(),
    );
  }
}

class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Path Helper')),
      body: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          Spacer(),
          Center(
            child: ElevatedButton(
              child: Text('Start'),
              onPressed: () {
                Navigator.push(
                  context,
                  MaterialPageRoute(builder: (context) => DirectionPanel()),
                );
              },
              style: ElevatedButton.styleFrom(
                padding: EdgeInsets.symmetric(horizontal: 40, vertical: 20),
                textStyle: TextStyle(fontSize: 24),
              ),
            ),
          ),
          Spacer(),
          Center(
            child: ElevatedButton(
              child: Text('Saved Directions'),
              onPressed: () {},
              style: ElevatedButton.styleFrom(
                primary: Colors.blue,
                padding: EdgeInsets.symmetric(horizontal: 30, vertical: 16),
              ),
            ),
          ),
          SizedBox(height: 30),
        ],
      ),
    );
  }
}

class DirectionPanel extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Direction Panel')),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            // Up Arrow
            IconButton(
              icon: Icon(Icons.arrow_upward),
              iconSize: 60,
              onPressed: () {},
            ),
            Row(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                IconButton(
                  icon: Icon(Icons.arrow_back),
                  iconSize: 60,
                  onPressed: () {},
                ),
                SizedBox(width: 40),
                ElevatedButton(
                  child: Text('OK'),
                  style: ElevatedButton.styleFrom(
                    primary: Colors.green,
                    minimumSize: Size(60, 60),
                  ),
                  onPressed: () {},
                ),
                SizedBox(width: 40),
                IconButton(
                  icon: Icon(Icons.arrow_forward),
                  iconSize: 60,
                  onPressed: () {},
                ),
              ],
            ),
            IconButton(
              icon: Icon(Icons.arrow_downward),
              iconSize: 60,
              onPressed: () {},
            ),
          ],
        ),
      ),
    );
  }
}