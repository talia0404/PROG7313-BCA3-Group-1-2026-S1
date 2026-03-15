## 📱 Tip Calculator App Introduction

This app is a beginner-friendly Android project that helps you practise working with **user input, calculations, button clicks, screen navigation, and multiple activities** in Android Studio using **XML layouts and Kotlin**.

The app starts with a **base feature**: calculating a tip from a bill amount and a tip percentage.

After that, you extend the app by adding an **extra feature**: splitting the bill and tip between multiple people. If the user chooses to split, the app moves to a second screen where they can choose whether the split should be **equal** or based on **different amounts**.

This project is nice because it starts simple, then levels up without becoming complete spaghetti chaos.

---

# 🎯 Base App Requirements

The base app should:

* allow the user to enter a **bill amount**
* allow the user to enter a **tip percentage**
* allow the user to press a **Calculate Tip** button
* calculate the tip
* display the tip in a **TextView**
* include a **Button, ImageView, TextView, and EditText**

---

# 🛠️ How to Implement the Base Feature

For the first version of the app, you only need **one screen**.

## Step 1: Design the layout

In `activity_main.xml`, add:

* an **ImageView** for decoration
* an **EditText** for the bill amount
* an **EditText** for the tip percentage
* a **Button** to calculate
* a **TextView** to show the result

## Step 2: Write the Kotlin logic

In `MainActivity.kt`:

* connect the Kotlin file to the XML layout using `setContentView()`
* use `findViewById()` to connect to the UI components
* read the values from the EditTexts
* convert the input into numbers
* calculate the tip using:

```text
tip = bill amount × tip percentage ÷ 100
```

* display the result in the TextView

---

# 💡 Base App Code

## `activity_main.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:gravity="center_horizontal"
        android:padding="24dp">

        <ImageView
            android:id="@+id/appImage"
            android:layout_width="120dp"
            android:layout_height="120dp"
            android:layout_marginBottom="16dp"
            android:src="@mipmap/ic_launcher"
            android:contentDescription="tip app image" />

        <TextView
            android:id="@+id/titleText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Tip Calculator"
            android:textSize="24sp"
            android:textStyle="bold"
            android:layout_marginBottom="20dp" />

        <EditText
            android:id="@+id/billInput"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter bill amount"
            android:inputType="numberDecimal"
            android:layout_marginBottom="16dp" />

        <EditText
            android:id="@+id/tipInput"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter tip percentage"
            android:inputType="numberDecimal"
            android:layout_marginBottom="20dp" />

        <Button
            android:id="@+id/calculateButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Calculate Tip"
            android:layout_marginBottom="20dp" />

        <TextView
            android:id="@+id/resultText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Tip amount will appear here"
            android:textSize="18sp" />

    </LinearLayout>
</ScrollView>
```

## `MainActivity.kt`

```kotlin
package com.example.tipcalculator

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    private lateinit var billInput: EditText
    private lateinit var tipInput: EditText
    private lateinit var calculateButton: Button
    private lateinit var splitButton: Button
    private lateinit var resultText: TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // connect this activity to the xml layout file
        setContentView(R.layout.activity_main)

        // link kotlin variables to the ui components in the layout
        billInput = findViewById(R.id.billInput)
        tipInput = findViewById(R.id.tipInput)
        calculateButton = findViewById(R.id.calculateButton)
        resultText = findViewById(R.id.resultText)

        // run this code when the calculate tip button is clicked
        calculateButton.setOnClickListener {

            // get the text entered by the user and convert it to strings
            val billText = billInput.text.toString()
            val tipText = tipInput.text.toString()

            // check that both fields were filled in
            if (billText.isNotEmpty() && tipText.isNotEmpty()) {

                // convert the user input into decimal numbers
                val billAmount = billText.toDouble()
                val tipPercentage = tipText.toDouble()

                // calculate the tip amount
                val tipAmount = billAmount * tipPercentage / 100

                // display the calculated tip in the textview
                resultText.text = "Tip amount: R%.2f".format(tipAmount)

            } else {

                // show a message if the user left a field empty
                resultText.text = "Please enter both values"
            }
        }
    }
}
```

---

# ➕ Added Feature: Split the Bill and Tip

Once you finish the base app, they can add the extension feature.

The new feature should:

* ask the user if they want to split the bill
* if yes, navigate to a **new screen**
* ask how many people to split between
* ask whether the split is:

  * **equal split**
  * **different amounts**
* calculate the result

For a beginner version, it is best to first implement **equal split**, then explain how **different amounts** could be added later.

---

# 🛠️ How to Implement the Added Feature

## Step 1: Add a second button to the main screen

Add a button such as:

**Split Bill**

This button will move the user to another activity.

## Step 2: Create a new activity

Create a second activity called:

`SplitBillActivity.kt`

This screen will contain:

* bill amount input
* tip percentage input
* number of people input
* a button for equal split
* a result TextView

## Step 3: Add navigation

In `MainActivity.kt`, create an `Intent` to move from `MainActivity` to `SplitBillActivity`.

## Step 4: Calculate the equal split

The formula becomes:

```text
tip = bill × tip percentage ÷ 100
total = bill + tip
per person = total ÷ number of people
```

## Step 5: Explain the different amounts version

A full different-amount split is a bit more advanced. You would need extra input fields so each person can pay a custom amount or percentage. For this intro app, it is fine to explain it as a future improvement after equal split is working.

---

# ✏️ Updated Main Screen with Split Button

## updated `activity_main.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:gravity="center_horizontal"
        android:padding="24dp">

        <ImageView
            android:id="@+id/appImage"
            android:layout_width="120dp"
            android:layout_height="120dp"
            android:layout_marginBottom="16dp"
            android:src="@mipmap/ic_launcher"
            android:contentDescription="tip app image" />

        <TextView
            android:id="@+id/titleText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Tip Calculator"
            android:textSize="24sp"
            android:textStyle="bold"
            android:layout_marginBottom="20dp" />

        <EditText
            android:id="@+id/billInput"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter bill amount"
            android:inputType="numberDecimal"
            android:layout_marginBottom="16dp" />

        <EditText
            android:id="@+id/tipInput"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter tip percentage"
            android:inputType="numberDecimal"
            android:layout_marginBottom="20dp" />

        <Button
            android:id="@+id/calculateButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Calculate Tip"
            android:layout_marginBottom="12dp" />

        <Button
            android:id="@+id/splitButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Split Bill"
            android:layout_marginBottom="20dp" />

        <TextView
            android:id="@+id/resultText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Tip amount will appear here"
            android:textSize="18sp" />

    </LinearLayout>
</ScrollView>
```

---

## updated `MainActivity.kt`

```kotlin
package com.example.tipcalculator

import android.content.Intent
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    private lateinit var billInput: EditText
    private lateinit var tipInput: EditText
    private lateinit var calculateButton: Button
    private lateinit var splitButton: Button
    private lateinit var resultText: TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // connect this activity to the xml layout
        setContentView(R.layout.activity_main)

        // link all the ui components to kotlin variables
        billInput = findViewById(R.id.billInput)
        tipInput = findViewById(R.id.tipInput)
        calculateButton = findViewById(R.id.calculateButton)
        splitButton = findViewById(R.id.splitButton)
        resultText = findViewById(R.id.resultText)

        // calculate the tip on the current screen
        calculateButton.setOnClickListener {
            val billText = billInput.text.toString()
            val tipText = tipInput.text.toString()

            if (billText.isNotEmpty() && tipText.isNotEmpty()) {
                val billAmount = billText.toDouble()
                val tipPercentage = tipText.toDouble()

                val tipAmount = billAmount * tipPercentage / 100

                resultText.text = "Tip amount: R%.2f".format(tipAmount)
            } else {
                resultText.text = "Please enter both values"
            }
        }

        // move to the split bill screen when the user clicks this button
        splitButton.setOnClickListener {
            val intent = Intent(this, SplitBillActivity::class.java)
            startActivity(intent)
        }
    }
}
```

---

# 👥 Split Screen Layout

## `activity_split_bill.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="24dp"
        android:gravity="center_horizontal">

        <TextView
            android:id="@+id/splitTitle"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Split Bill"
            android:textSize="24sp"
            android:textStyle="bold"
            android:layout_marginBottom="20dp" />

        <EditText
            android:id="@+id/splitBillInput"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter bill amount"
            android:inputType="numberDecimal"
            android:layout_marginBottom="16dp" />

        <EditText
            android:id="@+id/splitTipInput"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="Enter tip percentage"
            android:inputType="numberDecimal"
            android:layout_marginBottom="16dp" />

        <EditText
            android:id="@+id/peopleInput"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="How many people?"
            android:inputType="number"
            android:layout_marginBottom="20dp" />

        <Button
            android:id="@+id/equalSplitButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Equal Split"
            android:layout_marginBottom="12dp" />

        <Button
            android:id="@+id/differentSplitButton"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Different Amounts"
            android:layout_marginBottom="20dp" />

        <TextView
            android:id="@+id/splitResultText"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Split result will appear here"
            android:textSize="18sp" />

    </LinearLayout>
</ScrollView>
```

---

# ⚙️ Split Screen Logic

## `SplitBillActivity.kt`

```kotlin
package com.example.tipcalculator

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.TextView
import androidx.appcompat.app.AppCompatActivity

class SplitBillActivity : AppCompatActivity() {

    private lateinit var splitBillInput: EditText
    private lateinit var splitTipInput: EditText
    private lateinit var peopleInput: EditText
    private lateinit var equalSplitButton: Button
    private lateinit var differentSplitButton: Button
    private lateinit var splitResultText: TextView

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // connect this activity to the split screen layout
        setContentView(R.layout.activity_split_bill)

        // connect the kotlin variables to the xml components
        splitBillInput = findViewById(R.id.splitBillInput)
        splitTipInput = findViewById(R.id.splitTipInput)
        peopleInput = findViewById(R.id.peopleInput)
        equalSplitButton = findViewById(R.id.equalSplitButton)
        differentSplitButton = findViewById(R.id.differentSplitButton)
        splitResultText = findViewById(R.id.splitResultText)

        // calculate an equal split when the user clicks this button
        equalSplitButton.setOnClickListener {

            val billText = splitBillInput.text.toString()
            val tipText = splitTipInput.text.toString()
            val peopleText = peopleInput.text.toString()

            if (billText.isNotEmpty() && tipText.isNotEmpty() && peopleText.isNotEmpty()) {

                val billAmount = billText.toDouble()
                val tipPercentage = tipText.toDouble()
                val numberOfPeople = peopleText.toInt()

                if (numberOfPeople > 0) {

                    // calculate the tip
                    val tipAmount = billAmount * tipPercentage / 100

                    // calculate the total bill including tip
                    val totalAmount = billAmount + tipAmount

                    // divide the total equally between all people
                    val amountPerPerson = totalAmount / numberOfPeople

                    // show the answer in the textview
                    splitResultText.text =
                        "Each person pays: R%.2f".format(amountPerPerson)

                } else {
                    splitResultText.text = "Number of people must be more than 0"
                }

            } else {
                splitResultText.text = "Please fill in all fields"
            }
        }

        // this is a placeholder for the advanced feature
        // you can later create custom inputs for each person
        differentSplitButton.setOnClickListener {
            splitResultText.text = "Different amounts feature can be added next"
        }
    }
}
```

---

# 📋 Manifest Reminder

When adding a second screen, you must also register the new activity in `AndroidManifest.xml`.

## `AndroidManifest.xml`

```xml
<application
    ... >

    <activity android:name=".SplitBillActivity" />
    <activity android:name=".MainActivity">
        <intent-filter>
            <action android:name="android.intent.action.MAIN" />
            <category android:name="android.intent.category.LAUNCHER" />
        </intent-filter>
    </activity>

</application>
```


