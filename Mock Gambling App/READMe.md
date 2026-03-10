# 🎰 BetWise

### A Jetpack Compose Casino Session Tracker (PROG7313 Learning App)

![Android](https://img.shields.io/badge/Android-Jetpack%20Compose-green)
![Kotlin](https://img.shields.io/badge/Kotlin-Android-blue)
![RoomDB](https://img.shields.io/badge/Database-RoomDB-orange)
![Firebase](https://img.shields.io/badge/Cloud-Firebase-yellow)
![License](https://img.shields.io/badge/Education-Project-purple)

---

# 📱 Overview

**BetWise** is a **gambling-themed session tracker app** built for educational purposes.

Instead of building a traditional budgeting app, BetWise allows users to track **virtual casino sessions using fake chips**.

This makes the project more engaging while still covering all required app development concepts such as:

* authentication
* data capture
* Room database storage
* filtering and reporting
* charts and dashboards
* gamification
* Firebase integration
* GitHub version control
* automated testing

⚠️ **Important:**
This app **does not involve real gambling or real money**.
It is a **simulation app designed purely for learning Android development**.

---

# 🎯 Purpose of the App

The goal of BetWise is to help you practise building a **complete Android application**.

You will learn how to:

* design and build a multi-screen mobile application
* manage user input and validation
* persist data locally and online
* create interactive dashboards and reports
* implement gamification elements
* use GitHub professionally with CI/CD workflows

---

# 🎲 App Concept

BetWise is based on a **casino session tracking theme**.

Users log **virtual betting sessions** using fake chips. Each session records:

* the game category
* number of chips used
* session start and end time
* notes or description
* optional screenshot or photo

Users can then analyse their activity through **reports, graphs, and progress dashboards**.

Example categories include:

* 🎰 Slots
* ♠️ Poker
* 🎯 Roulette
* 🃏 Blackjack
* 🏈 Sports Picks

---

# 🚀 Main Features

## 🔐 User Authentication

Users can:

* register with a username and password
* log in securely
* log out of the application

This feature demonstrates authentication handling and navigation between screens.

---

## 🃏 Game Categories

Users can create and manage categories for different session types.

Example categories:

* Slots
* Poker
* Roulette
* Blackjack
* Lucky Wheel

Each session must belong to a category.

---

## 📝 Session Tracking

Users can log a gambling session with:

* session title
* chip amount
* date
* start time
* end time
* description
* category
* optional image

This simulates the **expense capture functionality required in the PoE**.

---

## 📸 Photo Attachment

Users can optionally attach a photo to a session entry.

Examples:

* game screenshots
* strategy notes
* fake receipts
* leaderboard images

This teaches You how to handle image selection and storage.

---

## 🎯 Chip Goals

Users can define monthly goals such as:

* minimum chip goal
* maximum chip limit
* category limits

These goals are used to track user performance.

---

## 📅 Session History

Users can view all sessions recorded during a **selected date range**.

The list view allows users to:

* see all recorded sessions
* open a session for detailed information
* view attached images

---

## 📊 Category Totals

The app calculates how many chips were used per category during a selected period.

This helps You practise:

* Room queries
* grouping records
* generating reports

---

## 📈 Graphs and Analytics

The final version of the app includes visual charts that display:

* daily chip usage
* category totals
* spending trends
* minimum and maximum goal markers

These graphs allow users to analyse their behaviour visually.

---

## 📊 Progress Dashboard

The dashboard shows:

* chips used this month
* current minimum and maximum goals
* categories that exceed limits
* overall progress

Overspending categories are highlighted visually.

---

## 🏆 Gamification

To make the app more engaging, BetWise includes a badge system.

Example rewards:

* 🥇 First Session Logged
* 🔥 7-Day Logging Streak
* 🎯 Stayed Within Goal
* 🃏 Category Explorer

This supports the gamification requirement of the PoE.

---

# 📱 App Screens

The app contains the following screens:

* Splash Screen
* Login Screen
* Register Screen
* Dashboard
* Categories
* Add Session
* Session List
* Session Details
* Goals
* Reports
* Graphs
* Rewards
* Settings

Navigation is implemented using **Jetpack Compose Navigation**.

---

# 🧠 Technology Stack

The application uses modern Android development tools:

| Technology         | Purpose                      |
| ------------------ | ---------------------------- |
| Kotlin             | Programming language         |
| Jetpack Compose    | UI development               |
| Navigation Compose | Screen navigation            |
| RoomDB             | Local database               |
| Firebase           | Online data storage          |
| ViewModel          | State management             |
| GitHub             | Version control              |
| GitHub Actions     | Automated builds and testing |

---

# 🗂 Project Structure

Example project structure:

```
com.betwise.app
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

This structure keeps the code clean and maintainable.

---

# 🖼 Screenshots

### Dashboard

![Dashboard Screenshot](screenshots/dashboard.png)

### Add Session

![Add Session Screenshot](screenshots/add_session.png)

### Reports

![Reports Screenshot](screenshots/reports.png)

### Graphs

![Graphs Screenshot](screenshots/graphs.png)

*(Replace these with real screenshots of your app.)*

---

# ⭐ Custom Features

The app also includes additional features beyond the minimum requirements.

## Feature 1 — Win/Loss Tracking

Each session records whether the user:

* won
* lost
* broke even

The app can display win/loss statistics.

---

## Feature 2 — Streak Rewards

Users earn rewards for consistent activity such as:

* logging sessions regularly
* staying within chip limits
* exploring multiple categories

---

# ⚙️ Installation

1. Clone the repository

```
git clone https://github.com/yourusername/betwise
```

2. Open the project in **Android Studio**

3. Sync Gradle dependencies

4. Run the application on:

* Android emulator
* Android device

---

# 🧪 Testing

Unit tests are included to test the core logic of the application.

Tests cover:

* database operations
* ViewModel logic
* data validation

Automated builds and tests are executed using **GitHub Actions**.

---

# 📹 Demonstration Video

A full demonstration video of the application can be viewed here:

```
(Add YouTube link here)
```

The video demonstrates:

* login and registration
* adding categories
* logging sessions
* attaching photos
* viewing reports
* graphs and dashboards
* gamification features

---

# ⚠️ Disclaimer

BetWise is an **educational project** created for the **PROG7313 module**.

The app:

* does **not involve real gambling**
* does **not use real money**
* does **not connect to betting services**

It is only intended to demonstrate Android development concepts.
