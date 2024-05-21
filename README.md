# How to create my first Flutter application with Android Studio

## 0. Prerequisistes

Install the **Flutter** and **Dart** plugins in Android Studio

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/8d4f0537-70f5-41f5-8caf-716bc8a98d98)

## 1. Run Android Studio

We select **Projects** and then **New Flutter Project**

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/f5120129-440b-49b5-8a6c-4b93db996827)

## 2. Select the Flutter installation path and press Next button

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/61665df3-009d-44a3-a73b-d26878916808)

## 3. We input the new project data

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/fe7c4378-30c3-4c62-96cb-7a9bcf95d227)

We see the folders and files new Flutter project structure

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/a17fc758-20e4-42ad-bf9d-221660a2ab29)


## 4. How to run the application in Chrome (web)

We 

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/7f61a3d3-e11b-4643-a10e-099cac036bbf)

We can verify the application running

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/e9b398ae-0146-4dd7-b57b-4398cf0547be)


## 5. How to run the application in 



## 6. Application Source Code

### 6.1. Import material library

We first import the **material.dart** library

```
import 'package:flutter/material.dart';
```

### 6.2. Run the application calling the main() function

We run the application inside the **main()** function:

```dart
void main() {
  runApp(const MyApp());
}
```

### 6.3. We create the application object extending the abstract class StatelessWidget 

We create a **StatelessWidget** object called **MyApp**:

```dart
class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}
```

As you see inside the **MyApp** StatelessWidget we set the application **title** and the application **theme**

Also inside the **MyApp** StatelessWidget we create a new **MyHomePage** StatefulWidget

### 6.4. We create a new page called "MyHomePage" extending the abstract class StatefulWidget

We create a new **State** inside the **MyHome**

```dart
class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}
```

### 6.5. We define the code for maniging the page MyHomePage state

```dart
class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text(widget.title),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),//
          ],//children: <Widget>
        ),//Column
      ),//body Center
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: const Icon(Icons.add),
      ), //floatingActionButton
    ); //Scaffold
  }//Widget build
}//class _MyHomePageState extends State<MyHomePage>
```

### 6.6. Application whole source code:

The application source code is defined in the file **lib/main.dart**:

**lib/main.dart**

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text(widget.title),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: const Icon(Icons.add),
      ), // This trailing comma makes auto-formatting nicer for build methods.
    );
  }
}
```
