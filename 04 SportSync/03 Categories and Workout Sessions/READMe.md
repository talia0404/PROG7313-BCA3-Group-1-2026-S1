# 🏋️ 02 — Workout Tracking

## 🎯 What you need to build

Create a feature where users can **log workout sessions** and track their training over time.

Each workout must include:

* workout name
* workout type (category)
* sport or fitness goal
* duration
* sets and repetitions
* notes
* workout date

This will allow users to build a **training history**.

---

# 🧠 Key Idea

A workout **must belong to at least one category**.

A **category = workout type**
Examples:

* Strength
* Cardio
* HIIT
* Mobility
* Sport-specific (e.g. Football Training)

---

# 🪜 Step 1 — Create Workout Categories

Users must be able to:

* create a category
* view categories
* select a category when logging a workout

Each category should include:

* category name
* optional description

---

# 🪜 Step 2 — Create the Workout Model

Each workout session must store:

* workout name
* selected category
* sport or goal
* duration
* sets
* reps
* notes
* date

Every workout **must be linked to a category**
(no category = invalid workout)

---

# 🪜 Step 3 — Store Data in RoomDB

You must create:

### 🧾 Category Entity

Represents workout types

Example:

* id
* name
* description

---

### 🧾 Workout Entity

Represents workout sessions

Example:

* id
* name
* categoryId (foreign key)
* goal
* duration
* sets
* reps
* notes
* date

---

### 🔗 Important Relationship

A workout must reference a category:

```
Workout -> Category
```

This is done using:

* `categoryId` inside the Workout table

---

# 🪜 Step 4 — Create DAO Functions

You will need:

### Category DAO

* insert category
* get all categories

### Workout DAO

* insert workout
* get workouts
* (optional) filter workouts by category 

---

# 🪜 Step 5 — Build the UI Flow

Users should be able to:

1️⃣ Create a category
2️⃣ View available categories
3️⃣ Add a workout
4️⃣ Select a category when adding a workout
5️⃣ View saved workouts

---

# 🧪 Step 6 — Test Your Feature

Test the following:

### Categories

* create multiple categories
* check they save correctly

### Workouts

* try adding a workout without a category → should not allow
* add a valid workout → should save
* close and reopen app → data should still be there

