# 🔗 Firebase & Flutter Connectivity Guide

This guide walks you through the steps to connect a Flutter app with Firebase.

---

## 🛠 Prerequisites

Make sure you have **Node.js** and **npm** installed.

Check your versions with the following commands:

```bash
node --version
npm --version
```

---

## 🌍 Install Firebase CLI Globally

To install the Firebase CLI globally, run:

```bash
npm install -g firebase-tools
```

---

## 🚀 Create a Flutter Project

1. Create a new Flutter project (or open an existing one):

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

> Make sure to log in with the same account you'll use for your Firebase project.

---

## 🎯 Create a Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com).
2. Click **Add Project** and follow the setup steps.

---

## ✅ Check Firebase Project Connection

In your Flutter terminal, verify connection using:

```bash
firebase projects:list
```

This lists all your Firebase projects.

---

## 🔄 Connect Flutter to Firebase

Activate FlutterFire CLI globally:

```bash
dart pub global activate flutterfire_cli
```

Then, connect your Flutter app with Firebase:

```bash
flutterfire configure
```

> ⚠️ If the command doesn't work, make sure your environment PATH is set correctly.

Use `⬆️` and `⬇️` to navigate, `Space` to select platforms (select Android and iOS), then `Enter` to proceed.

---

## 📦 Add Dependencies

In your `pubspec.yaml`, add the following:

```yaml
dependencies:
  firebase_core: ^latest_version
  firebase_analytics: ^latest_version
```

or ADD Below Commands
```
flutter pub add firebase_core
```

```
flutter pub add firebase_analytics
```

Then run:

```bash
flutter pub get
```

---

## 🎉 You’re all set!

Firebase is now connected to your Flutter app. You can now begin using Firebase services like Firestore, Auth, and more.

---


Open main.dart

import below Commands

```dart
import 'package:firebase_core/firebase_core.dart';
```

```dart
import 'firebase_options.dart';
```



add this code in main.dart

```dart
void main() async {
  WidgetsFlutterBinding.ensureInitialized();
  await Firebase.initializeApp(options: DefaultFirebaseOptions.currentPlatform);
  runApp(const MainApp());
}
```