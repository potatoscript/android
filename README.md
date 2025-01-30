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
