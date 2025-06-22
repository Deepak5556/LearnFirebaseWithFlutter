# 🔗 Firebase & Flutter Connectivity Guide

This guide walks you through the complete process of connecting a Flutter app to Firebase.

---

## 🛠 Prerequisites

Make sure you have **Node.js**, **npm**, and **Flutter SDK** installed.

Check the versions using:

```bash
node --version
npm --version
flutter --version
```

---

## 🌍 Install Firebase CLI Globally

To install the Firebase CLI globally, run:

```bash
npm install -g firebase-tools
```

---

## 🚀 Create a Flutter Project

1. Create a new Flutter project or open an existing one:

```bash
flutter create my_project
cd my_project
```

2. Open your Flutter project in your preferred IDE or code editor.

---

## 🔐 Firebase Login

Log in to Firebase from the terminal:

```bash
firebase login
```

> Make sure to log in with the same Google account you'll use for your Firebase project.

---

## 🎯 Create a Firebase Project

1. Go to the [Firebase Console](https://console.firebase.google.com).
2. Click **Add Project** and follow the setup instructions.

---

## ✅ Check Firebase Project Connection

To verify your Firebase projects from the terminal:

```bash
firebase projects:list
```

---

## 🔄 Connect Flutter to Firebase

### Step 1: Activate FlutterFire CLI globally

```bash
dart pub global activate flutterfire_cli
```

### Step 2: Configure Firebase for your Flutter app

```bash
flutterfire configure
```

> Use the arrow keys to select platforms (✅ Android, iOS). Press **Space** to select and **Enter** to confirm.

If the command doesn’t work, ensure your `PATH` includes the Dart pub cache:

**Windows example:**

```bash
setx PATH "%PATH%;C:\Users\<YourUser>\AppData\Local\Pub\Cache\bin"
```

---

## 📦 Add Firebase Dependencies

Add dependencies using terminal:

```bash
flutter pub add firebase_core
flutter pub add firebase_analytics
```

Or manually in `pubspec.yaml`:

```yaml
dependencies:
  firebase_core: ^2.0.0
  firebase_analytics: ^10.0.0
```

Then run:

```bash
flutter pub get
```

---

## 🔌 Initialize Firebase in `main.dart`

### Step 1: Import required packages

```dart
import 'package:flutter/material.dart';
import 'package:firebase_core/firebase_core.dart';
import 'firebase_options.dart';
```

### Step 2: Initialize Firebase

Update your `main()` function as shown:

```dart
void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp(
    options: DefaultFirebaseOptions.currentPlatform,
  );
  runApp(const MainApp());
}
```

---

## 🎉 You’re All Set!

Firebase is now connected to your Flutter app.  
You can start integrating services like:

- 🔐 Authentication
- 📦 Firestore
- ☁️ Cloud Storage
- 📊 Analytics

Happy coding! 🚀
