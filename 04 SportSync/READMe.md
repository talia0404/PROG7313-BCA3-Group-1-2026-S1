# 🏋️‍♂️ SportSync

### A Jetpack Compose Sports Training & Fitness Tracker (PROG7313 Learning App)

![Android](https://img.shields.io/badge/Android-Jetpack%20Compose-green)
![Kotlin](https://img.shields.io/badge/Kotlin-Android-blue)
![RoomDB](https://img.shields.io/badge/Database-RoomDB-orange)
![Firebase](https://img.shields.io/badge/Cloud-Firebase-yellow)
![License](https://img.shields.io/badge/Education-Project-purple)

---

# 📱 Overview

**SportSync** is a **sports training and fitness tracking app** designed to help users manage workouts, track nutrition, and improve athletic performance.

The app adapts to the user's training style. A user can either:

* train for a **specific sport**
* follow a **general gym fitness plan**

If a user is an **athlete**, the app recommends exercises that support their sport.  
If they are simply **going to the gym**, the workouts focus on their goals such as:

* building muscle
* losing weight
* improving endurance
* increasing strength

Users can also **switch between sport training and normal gym workouts** depending on their training needs.

This project helps you practise building a **complete modern Android application** while implementing key development concepts such as:

* authentication
* data capture
* Room database storage
* filtering and reporting
* charts and dashboards
* gamification
* Firebase integration
* GitHub version control
* automated testing

---

# 🎯 Purpose of the App

The goal of **SportSync** is to help you practise building a **full-featured Android application using Jetpack Compose**.

You will learn how to:

* design and build a multi-screen mobile application
* manage user input and validation
* store and retrieve data locally
* integrate cloud services
* build dashboards and reports
* implement recommendation logic
* add gamification features
* manage a professional GitHub project

---

# 🏃 App Concept

SportSync is based on a **training assistant concept**.

The app helps users manage their **fitness training and nutrition in one place**.

When a user creates an account, they can choose:

* a **specific sport** they are training for  
or
* **general fitness / gym training**

The app will then **recommend workouts based on that choice**.

Examples:

### Sport Training Mode

If a user selects a sport such as:

* ⚽ Football
* 🏀 Basketball
* 🏃 Athletics
* 🥊 Boxing
* 🏉 Rugby

The app recommends exercises that support performance in that sport.

Example recommendations:

* agility drills
* sprint training
* endurance workouts
* explosive strength exercises
* mobility and recovery routines

---

### Gym Training Mode

If a user chooses general gym training, the app focuses on their fitness goals.

Example goals:

* 💪 Build muscle
* 🔥 Lose weight
* 🫀 Improve endurance
* 🏋️ Increase strength

The workout recommendations change depending on the goal.

Athletes can **switch between sport training and gym workouts** whenever needed.

---

# 🚀 Main Features

## 01 🔐 User Authentication

Users can:

* register with a username and password
* log in securely
* log out of the application

This demonstrates user authentication and screen navigation.

---

## 02 🏋️ Workout Tracking

Users can log workouts including:

* workout name
* workout type
* sport or fitness goal
* duration
* sets and repetitions
* notes
* workout date

This allows users to build a **training history** over time.

---

## 03 🧠 Training Recommendations

The app recommends exercises based on:

* selected sport
* training goals
* past workouts

Example recommendations:

* strength workouts
* cardio routines
* sport-specific drills
* recovery sessions

This feature simulates **basic recommendation logic** in the application.

---

## 04 🍎 Food & Nutrition Tracker

Users can track meals and calorie intake.

Meal entries include:

* meal name
* calories
* protein
* carbohydrates
* fats
* meal category (breakfast, lunch, dinner, snack)

The app can also **recommend meals based on fitness goals**.

Example:

* high protein meals for muscle gain
* calorie deficit meals for weight loss
* balanced meals for endurance athletes

---

## 05 🧾 Ingredient-Based Meal Suggestions

Users can enter ingredients they have available.

Example:

```

Chicken
Rice
Spinach
Eggs

```

The app can suggest possible meals that can be made using those ingredients.

This feature demonstrates **basic filtering and recommendation logic**.

---

## 06 🗺 Nearby Gyms

The app can show **gyms near the user's location**.

Users can:

* view nearby gym locations
* see gym details
* save favourite gyms

This introduces **location-based features**.

---

## 07 📅 Workout History

Users can view workouts logged during a **selected date range**.

The list view allows users to:

* see all recorded workouts
* open a workout for details
* review training progress

---

## 08 📊 Performance Reports

The app can generate reports such as:

* workouts completed per week
* workout categories used
* calories burned
* nutrition trends

This helps practise:

* database queries
* filtering data
* generating reports

---

## 09 📈 Graphs and Analytics

Graphs can display information such as:

* workouts per week
* calories consumed
* calories burned
* workout duration trends
* training consistency

This allows users to **visualise their progress**.

---

## 10 📊 Progress Dashboard

The dashboard displays:

* total workouts completed
* current fitness goals
* calorie intake vs targets
* training streaks

This gives users a **quick overview of their performance**.

---

## 11 🏆 Gamification

To make the app more engaging, SportSync includes a reward system.

Example achievements:

* 🥇 First Workout Logged
* 🔥 7-Day Training Streak
* 💪 Strength Milestone
* 🥗 Healthy Eating Streak

Gamification helps motivate users to stay consistent.

---

# 📱 App Screens

The app contains multiple screens including:

* Splash Screen
* Login Screen
* Register Screen
* Dashboard
* Workout Tracker
* Workout History
* Add Workout
* Food Tracker
* Ingredient Meal Finder
* Nearby Gyms
* Reports
* Graphs
* Rewards
* Settings

Navigation is implemented using **Jetpack Compose Navigation**.

---

# 🧠 Technology Stack

The application uses modern Android development tools.

| Technology         | Purpose                      |
|------------------|-----------------------------|
| Kotlin           | Programming language        |
| Jetpack Compose  | UI development              |
| Navigation Compose | Screen navigation         |
| RoomDB           | Local database              |
| Firebase         | Cloud data storage          |
| ViewModel        | State management            |
| GitHub           | Version control             |
| GitHub Actions   | Automated builds and tests  |

---

# 🗂 Project Structure

Example project structure:

```

com.sportsync.app
│
├── data
│   ├── database
│   ├── dao
│   ├── entities
│
├── repository
│
├── ui
│   ├── screens
│   ├── components
│   ├── theme
│
├── navigation
│
├── viewmodel
│
└── MainActivity.kt

```

This structure keeps the code organised and maintainable.

---

# 🧪 Testing

Unit tests are included to test the core logic of the application.

Tests cover:

* database operations
* ViewModel logic
* data validation

Automated builds and tests are executed using **GitHub Actions**.

---

SportSync is an educational project created for the **PROG7313 module**, designed to help you practise building a **complete Android application using modern development tools**.

