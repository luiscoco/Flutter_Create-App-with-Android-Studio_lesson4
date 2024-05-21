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

We select **Chrome (web)** in the dropdown list:

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/7f61a3d3-e11b-4643-a10e-099cac036bbf)

We can verify the application is running

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/e9b398ae-0146-4dd7-b57b-4398cf0547be)

## 5. How to run the application in Windows (desktop)

We select **Windows (desktop)** in the dropdown list:

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/df5876c5-f8a1-43a7-b71e-e8d2c47e15d6)

## 6. How to run the application in a Mobile Device Simulator

We select the **Device Manager** button

We create a new Device pressing the button **Create Device**

After creating the device we select the **Launch this AVD in the emulator** button

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/7a4aadc5-3e86-4ac2-b6de-a6b30a9daf53)

We can see the new Mobile Device Simulator is running

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/1641824c-25bc-43f1-bf30-2b396e2c1f65)

If we want to increase the Device size we first press in the **Window** button

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/13cfe571-c384-48db-a7d7-5b5d6c3cce40)

Then we have separate window for the device 

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/c76cdf9f-55db-414c-8f58-a8a09f1466c0)

Now for running the application we select the device in the dropdonw list **Pixel 7 PRO API 34 (mobile)** and then we press the **play** button 

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/a736d742-e2f9-405d-a206-658df712c6e0)

We verify the application in running in the Mobile simulator

We press the **+** button and we see the counter value is increasing each time we press that button

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/8a0dcf82-8b0f-40cd-8da6-d62a9c85808d)

![image](https://github.com/luiscoco/Flutter_Create-App-with-Android-Studio_lesson4/assets/32194879/05874382-71c9-443f-a58d-cf9bf8bb9b46)

## 7. Application Source Code

### 7.1. Import material library

We first import the **material.dart** library

```
import 'package:flutter/material.dart';
```

### 7.2. Run the application calling the main() function

We run the application inside the **main()** function:

```dart
void main() {
  runApp(const MyApp());
}
```

### 7.3. We create the application object extending the abstract class StatelessWidget 

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

### 7.4. We create a new page called "MyHomePage" extending the abstract class StatefulWidget

We create a new **State** inside the **MyHome**

```dart
class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}
```

### 7.5. We define the code for maniging the page MyHomePage state

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

### 7.6. Application whole source code:

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
