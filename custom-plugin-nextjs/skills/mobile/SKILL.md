---
name: mobile-skills
description: Master iOS development with Swift, Android development with Kotlin, React Native, Flutter, and cross-platform mobile technologies.
---

# Mobile Development Skills

## iOS Development (Swift)

```swift
import SwiftUI

struct ContentView: View {
  @State private var count = 0

  var body: some View {
    VStack {
      Text("Count: \(count)")
        .font(.headline)
      Button(action: { count += 1 }) {
        Text("Increment")
      }
    }
  }
}

// MVVM Pattern
@MainActor
class ViewModel: ObservableObject {
  @Published var items: [Item] = []

  func fetchItems() async {
    let data = await APIService.getItems()
    self.items = data
  }
}
```

## Android Development (Kotlin)

```kotlin
import androidx.compose.material3.*
import androidx.compose.runtime.*

@Composable
fun CounterApp() {
  var count by remember { mutableStateOf(0) }

  Scaffold(
    topBar = { TopAppBar(title = { Text("Counter") }) }
  ) { padding ->
    Box(modifier = Modifier.padding(padding)) {
      Button(onClick = { count++ }) {
        Text("Count: $count")
      }
    }
  }
}

// ViewModel
class CounterViewModel : ViewModel() {
  private val _count = MutableStateFlow(0)
  val count: StateFlow<Int> = _count.asStateFlow()
}
```

## React Native Basics

```javascript
import React, {useState} from 'react';
import {View, Text, Button, ScrollView} from 'react-native';

export default function App() {
  const [count, setCount] = useState(0);

  return (
    <ScrollView>
      <Text style={{fontSize: 20}}>Count: {count}</Text>
      <Button
        title="Increment"
        onPress={() => setCount(count + 1)}
      />
    </ScrollView>
  );
}
```

## Flutter Development (Dart)

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(home: CounterPage());
  }
}

class CounterPage extends StatefulWidget {
  @override
  _CounterPageState createState() => _CounterPageState();
}

class _CounterPageState extends State<CounterPage> {
  int count = 0;

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('Counter')),
      body: Center(
        child: Column(children: [
          Text('Count: $count', style: TextStyle(fontSize: 20)),
          ElevatedButton(
            onPressed: () => setState(() => count++),
            child: Text('Increment'),
          ),
        ]),
      ),
    );
  }
}
```

## Navigation Pattern

```javascript
// React Navigation
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';

const Stack = createNativeStackNavigator();

function Navigation() {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
        <Stack.Screen name="Details" component={DetailsScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}
```

## Networking in Mobile

```javascript
// Fetch API
const fetchData = async () => {
  try {
    const response = await fetch('https://api.example.com/data');
    const data = await response.json();
    return data;
  } catch (error) {
    console.error(error);
  }
};
```

## State Management

- **React Native**: Redux, Zustand, Jotai
- **Flutter**: Provider, Riverpod, Bloc
- **iOS**: SwiftUI @State, @StateObject
- **Android**: ViewModel, LiveData, StateFlow

## Mobile Best Practices

- **Performance**: Optimize bundle size, lazy loading
- **Battery**: Minimize background operations
- **Offline**: Support offline-first sync
- **Accessibility**: VoiceOver/TalkBack support
- **Security**: Keychain/Keystore for secrets
- **Testing**: Unit, widget, and integration tests

## App Store Deployment

**iOS:**
1. Create Apple ID
2. Generate certificates
3. Build archive
4. Submit to TestFlight
5. App Store release

**Android:**
1. Generate key store
2. Build release APK/AAB
3. Create Play Store listing
4. Upload with screenshots
5. Gradual rollout

## Key Concepts Checklist

- [ ] SwiftUI/Compose UI basics
- [ ] State management patterns
- [ ] Navigation stacks
- [ ] Network requests
- [ ] Local storage (preferences, databases)
- [ ] Async operations
- [ ] Error handling
- [ ] Loading states
- [ ] Testing strategies
- [ ] Performance optimization
- [ ] App store requirements
- [ ] Code signing
- [ ] Debugging tools

---

**Source**: https://roadmap.sh
