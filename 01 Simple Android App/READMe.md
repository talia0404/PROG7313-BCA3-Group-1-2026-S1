## 📱 Introduction to Android Studio & Kotlin

Welcome to Android app development. This is where your code stops living quietly on a laptop and starts running on a mobile device in someone’s pocket.

Android apps are built using **Android Studio**, which is the official development environment (IDE) for Android development. An IDE is a software tool that helps developers write code, design user interfaces, run applications, and debug errors in one place.

Most modern Android apps are written using **Kotlin**. Kotlin is a programming language developed by JetBrains and officially supported by Google for Android development. If you have previously worked with languages such as Java or C#, many concepts will feel familiar because Kotlin also supports **object-oriented programming**, but it allows developers to write cleaner and more concise code.

In traditional Android development (before Jetpack Compose), apps are built using two main parts:

**1️⃣ XML Layouts**
These define what the screen looks like — buttons, text, images, and other user interface elements.

**2️⃣ Kotlin Code**
This controls how the app behaves — for example, what happens when a user presses a button.

Think of it like this:

* **XML = appearance**
* **Kotlin = behaviour**

Together they form a complete Android application.

For more information about how Android screens work, you can read Google's official documentation on **Activities** here:

[https://developer.android.com/guide/components/activities/intro-activities](https://developer.android.com/guide/components/activities/intro-activities)

Activities are one of the core building blocks of Android applications and represent a single screen in an app.

---

# 🚀 Creating Your First Android App

In this example, we will create a simple Android application that displays a message when a button is pressed.

---

# Step 1: Create a New Project 🧱

1. Open **Android Studio**

2. Click **New Project**

3. Select **Empty Views Activity**
   *(Ensure you do not select Jetpack Compose)*

4. Configure the project:

| Setting     | Value             |
| ----------- | ----------------- |
| Name        | MyFirstAndroidApp |
| Language    | Kotlin            |
| Minimum SDK | API 24 or higher  |

Click **Finish** and allow Android Studio to build the project.

Android Studio will automatically generate the initial project structure.

---

# Step 2: Understand the Project Structure 🗂️

Two important files are created automatically.

### MainActivity.kt

This file contains the **Kotlin logic** for your application.

Location:

```
app > java > yourpackage > MainActivity.kt
```

---

### activity_main.xml

This file defines the **user interface layout**.

Location:

```
app > res > layout > activity_main.xml
```

---

# Step 3: Design the User Interface 🎨

Open:

```
res > layout > activity_main.xml
```

Replace the code with the following layout:

```xml
<?xml version="1.0" encoding="utf-8"?>

<!-- Root layout that arranges components vertically -->
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <!-- TextView to display a message -->
    <TextView
        android:id="@+id/messageText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello Android!"
        android:textSize="24sp"
        android:layout_marginBottom="20dp"/>

    <!-- Button the user can press -->
    <Button
        android:id="@+id/changeButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Click Me"/>

</LinearLayout>
```

### What this layout contains

**LinearLayout**
A container that arranges UI elements vertically.

**TextView**
Displays text to the user.

**Button**
Allows the user to perform an action.

Each component has an **ID**, which allows it to be accessed in Kotlin code.

---

# Step 4: Add Kotlin Functionality ⚙️

Now we will add behaviour so that when the button is pressed, the text changes.

Open:

```
MainActivity.kt
```

Replace the code with the following:

```kotlin
package com.example.myfirstandroidapp

import android.os.Bundle
import android.widget.Button
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {

        // Called when the activity is created
        super.onCreate(savedInstanceState)

        // Connect the activity to the XML layout
        setContentView(R.layout.activity_main)

        // Access UI components from the layout using their IDs
        val messageText = findViewById<TextView>(R.id.messageText)
        val changeButton = findViewById<Button>(R.id.changeButton)

        // Detect when the button is clicked
        changeButton.setOnClickListener {

            // Change the text displayed in the TextView
            messageText.text = "Welcome to Android Development!"

        }
    }
}
```

### What this code does

`setContentView()`
Links the Kotlin activity to the XML layout.

`findViewById()`
Allows Kotlin code to access UI elements created in XML.

`setOnClickListener()`
Runs code when the button is pressed.

When the user taps the button, the text displayed on the screen changes.

---

# Step 5: Run the App ▶️

To run the application:

1. Click the **Run (▶)** button in Android Studio.
2. Select a **virtual device** or a **physical Android phone**.
3. Wait for the app to build and launch.

You should now see:

* A message displayed on the screen
* A button below the message
* When the button is pressed, the message changes

You have successfully created your first Android application.
