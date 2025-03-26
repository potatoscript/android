# **Android Java Cheat Sheet**

| Feature                         | Description                                   |  
|---------------------------------|-----------------------------------------------|  
| [Auto Detect Updated Version of App](https://github.com/potatoscript/android/wiki/Update-App) | Automatically check and update app versions. |  
| [Button](https://github.com/potatoscript/android/wiki/Button) | Implement `onClick` functionality for buttons. |  
| [Camera](https://github.com/potatoscript/android/wiki/Camera) | Capture photos using the device camera. |  
| [Call a Method in MainActivity from Another Class](https://github.com/potatoscript/android/wiki/Call-Method-with-instance) | Use an instance to retrieve values or call methods from another class. |  
| [Chart](https://github.com/potatoscript/android/wiki/Chart) | Create charts using the [MPAndroidChart](https://github.com/PhilJay/MPAndroidChart) library. |  
| [Color Picker](https://github.com/potatoscript/android/wiki/Color-Picker) | Select colors from a palette using `onTouch` events. |  
| [Connect to MySQL](https://github.com/potatoscript/android/wiki/Connect-to-MySQL) | Implement login functionality with PHP and MySQL. |  
| [Connect to SQLite](https://github.com/potatoscript/android/wiki/Connect-to-SQLite) | Use SQLite for local device database management. |  
| [Delay Handler](https://github.com/potatoscript/android/wiki/Delay) | Use `postDelayed` to handle delays. |  
| [Drag and Drop with ButterKnife](https://github.com/potatoscript/android/wiki/Drag-n-Drop) | Simplify drag-and-drop using the ButterKnife library. |  
| [Drag, Drop, and Swipe](https://github.com/potatoscript/android/wiki/Drag-n-Drop-Swipe) | Implement drag, drop, and swipe item features. |  
| [EditText](https://github.com/potatoscript/android/wiki/EditText) | Work with input fields effectively. |  
| [Gestures](https://github.com/potatoscript/android/wiki/Gestures) | Detect and respond to gesture inputs. |  
| [GridLayout](https://github.com/potatoscript/android/wiki/GridLayout) | Design layouts using a grid structure. |  
| [ImageView](https://github.com/potatoscript/android/wiki/ImageView) | Load images from the server or internet URLs. |  
| [List](https://github.com/potatoscript/android/wiki/List) | Implement and manage lists in your app. |  
| [Page Changing](https://github.com/potatoscript/android/wiki/Page-Changing) | Navigate between pages or activities. |  
| [Publish to Play Store Console](https://github.com/potatoscript/android/wiki/Public-to-Play-Store) | Guide for publishing your app on the Play Store. |  
| Random Number                  | Use `final int dice1 = new Random().nextInt(6) + 1;` to generate numbers in the range `[1,6]`. |  
| [RecyclerView](https://github.com/potatoscript/android/wiki/RecyclerView) | Create dynamic and efficient lists using RecyclerView. |  
| [Repeat Method](https://github.com/potatoscript/android/wiki/Repeat) | Use `Runnable` to execute repeated tasks. |  
| [Show Keyboard for Older Devices](https://github.com/potatoscript/android/wiki/Show-Keyboard-in-old-handphone) | Fix keyboard issues on older phones. |  
| [Sound](https://github.com/potatoscript/android/wiki/Sound) | Add music or sound effects to your app. |  
| [String](https://github.com/potatoscript/android/wiki/String) | Split and manipulate strings efficiently. |  
| [Toolbar Menu](https://github.com/potatoscript/android/wiki/Toolbar) | Create and customize a toolbar menu. |  
| [Toolbar Search Item](https://github.com/potatoscript/android/wiki/Toolbar-Search-Item) | Add and configure a search item in the toolbar. |  
| [QR Code Generator](https://github.com/potatoscript/android/wiki/QR-Code-Making) | Generate custom QR codes in your app. |  
| [QR Code Scanner](https://github.com/potatoscript/android/wiki/QR-Scanner) | Scan QR codes and barcodes. |  

---


# [Android Java Tutorial](https://github.com/potatoscript/android/wiki)

## Table of Contents
- [Introduction](#introduction)
- [Setting Up the Environment](#setting-up-the-environment)
- [Creating a New Android Project](#creating-a-new-android-project)
- [Understanding Project Structure](#understanding-project-structure)
- [Building a Basic Android App](#building-a-basic-android-app)
- [Activities and Intents](#activities-and-intents)
- [Layouts and Views](#layouts-and-views)
- [Handling User Input](#handling-user-input)
- [RecyclerView and Adapters](#recyclerview-and-adapters)
- [Working with SQLite Database](#working-with-sqlite-database)
- [Networking and API Calls](#networking-and-api-calls)
- [Using Firebase for Authentication](#using-firebase-for-authentication)
- [Working with Services and Broadcast Receivers](#working-with-services-and-broadcast-receivers)
- [Managing Background Tasks with WorkManager](#managing-background-tasks-with-workmanager)
- [Implementing Notifications](#implementing-notifications)
- [Publishing Your App](#publishing-your-app)
- [Conclusion](#conclusion)

---

## Introduction
Android development using Java is a robust way to build mobile applications. This guide will take you step by step through setting up your environment, creating an Android project, and building complete applications with real-world functionality.

---

## Setting Up the Environment
### 1. Install Android Studio
- Download and install [Android Studio](https://developer.android.com/studio)
- Ensure you have Java JDK installed (Android Studio includes OpenJDK by default)

### 2. Configure Android SDK
- Open Android Studio and go to `Preferences > Appearance & Behavior > System Settings > Android SDK`
- Install necessary SDKs for your target Android versions
- Install necessary dependencies such as `Google Play Services` and `Android Emulator`

---

## Creating a New Android Project
### 1. Open Android Studio and create a new project
- Choose `Empty Activity`
- Set `Language: Java`
- Set `Minimum SDK: API 21 (Lollipop)`
- Click `Finish`

### 2. Run the Default App
- Click on `Run` ▶ to launch the app on an emulator or a real device

---

## Understanding Project Structure
```
MyApp/
├── manifests/       # AndroidManifest.xml (App configurations)
├── java/com/example/myapp/  # Java source code
├── res/             # Layouts, drawables, and resources
│   ├── layout/      # XML layout files
│   ├── values/      # Strings, colors, styles
├── build.gradle     # Build configuration
```

---

## Building a Basic Android App
### 1. Modify `activity_main.xml`
```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello, Android!"
        android:textSize="24sp" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Click Me" />
</LinearLayout>
```

### 2. Modify `MainActivity.java`
```java
package com.example.myapp;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        TextView textView = findViewById(R.id.textView);
        Button button = findViewById(R.id.button);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                textView.setText("Button Clicked!");
            }
        });
    }
}
```

### 3. Run the App
- Click `Run` ▶ to see the changes

---

## Activities and Intents
- **Activity**: A single screen with UI
- **Intent**: A way to navigate between activities

### Example: Open a Second Activity
#### 1. Create `SecondActivity.java`
```java
package com.example.myapp;

import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;

public class SecondActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);
    }
}
```

#### 2. Modify `AndroidManifest.xml`
```xml
<activity android:name=".SecondActivity" />
```

#### 3. Start Second Activity from MainActivity
```java
Intent intent = new Intent(MainActivity.this, SecondActivity.class);
startActivity(intent);
```

---

## Managing Background Tasks with WorkManager
WorkManager allows you to schedule background tasks efficiently.

### Example: Background Task Execution
```java
public class MyWorker extends Worker {
    public MyWorker(@NonNull Context context, @NonNull WorkerParameters workerParams) {
        super(context, workerParams);
    }

    @NonNull
    @Override
    public Result doWork() {
        Log.d("WorkManager", "Background task executed");
        return Result.success();
    }
}
```

---

## Publishing Your App
1. Generate Signed APK via `Build > Generate Signed APK`
2. Register on Google Play Console
3. Upload APK and publish

---

## Conclusion
This guide covers everything from setting up Android Studio to creating a functional Android app. Keep experimenting with more advanced features like databases, networking, Firebase, and background task management!
