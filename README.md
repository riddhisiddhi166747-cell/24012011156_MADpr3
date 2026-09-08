# Practical-3: Implicit & Explicit Intent in Android

## 📌 Aim

Create an Android application using **Kotlin** that demonstrates the use of **Implicit Intent and Explicit Intent**.

The application provides buttons to perform the following operations:

1. Make a call to a specific number
2. Open a specific URL
3. Open Call Log
4. Open Gallery
5. Set an Alarm
6. Open Camera
7. Open Login Activity

---

## 📝 Description

An **Intent** in Android is a messaging object used to request an action from another Android component.

In this practical, both **Implicit Intent** and **Explicit Intent** are demonstrated.

### Implicit Intent

An implicit intent does not specify a particular application or component. Instead, it describes an action that should be performed, and Android finds a suitable application to handle it.

Examples:

- Opening a website
- Opening the call log
- Opening the gallery
- Opening the camera
- Setting an alarm

### Explicit Intent

An explicit intent specifies the exact component or Activity that should be started.

Example:

- Opening the `LoginActivity` from the main Activity.

---

# 🎯 Operations Performed

## 1. Make Call to Specific Number

The application uses an Intent with the `tel:` URI to open the phone dialer for a specific number.

Example:

```kotlin
val intent = Intent(Intent.ACTION_DIAL)
intent.data = Uri.parse("tel:1234567890")
startActivity(intent)
```

---

## 2. Open Specific URL

An implicit Intent is used to open a website in the device's web browser.

Example:

```kotlin
val intent = Intent(Intent.ACTION_VIEW)
intent.data = Uri.parse("https://www.google.com")
startActivity(intent)
```

---

## 3. Open Call Log

The Call Log application is opened using an implicit Intent.

Example:

```kotlin
val intent = Intent(Intent.ACTION_VIEW)
intent.type = CallLog.Calls.CONTENT_TYPE
startActivity(intent)
```

---

## 4. Open Gallery

The device gallery/image picker is opened using an implicit Intent.

Example:

```kotlin
val intent = Intent(Intent.ACTION_VIEW)
intent.type = "image/*"
startActivity(intent)
```

---

## 5. Set Alarm

The Android Alarm application is opened using an Intent.

Example:

```kotlin
val intent = Intent(AlarmClock.ACTION_SET_ALARM)
intent.putExtra(AlarmClock.EXTRA_MESSAGE, "My Alarm")
intent.putExtra(AlarmClock.EXTRA_HOUR, 7)
intent.putExtra(AlarmClock.EXTRA_MINUTES, 0)
startActivity(intent)
```

---

## 6. Open Camera

An Intent is used to launch the camera application.

Example:

```kotlin
val intent = Intent(MediaStore.ACTION_IMAGE_CAPTURE)
startActivity(intent)
```

For newer Android versions, appropriate camera permission handling may be required depending on how the camera is accessed.

---

## 7. Open Login Activity

An explicit Intent is used to navigate from the main Activity to the Login Activity.

Example:

```kotlin
val intent = Intent(this, LoginActivity::class.java)
startActivity(intent)
```

---

# 📚 Topics Studied

The following Android concepts are covered in this practical:

- Intent
- Implicit Intent
- Explicit Intent
- Intent Actions
- `Intent.setData()`
- `Intent.setType()`
- `Button`
- `ConstraintLayout`
- `CoordinatorLayout`
- `startActivity()`
- `ActivityResultContracts`
- Permissions in Android Manifest
- `ContextCompat.checkSelfPermission()`
- `ActivityCompat.requestPermissions()`
- `Uri.parse()`
- `ContactsContract.Contacts.CONTENT_TYPE`
- `CallLog.Calls.CONTENT_TYPE`
- `"image/*"`
- `"tel:"`

---

# 🔑 Important Intent Components

| Component | Purpose |
|---|---|
| `Intent` | Used to request an action |
| `Intent.ACTION_VIEW` | View/open content |
| `Intent.ACTION_DIAL` | Open phone dialer |
| `Intent.ACTION_MAIN` | Start main activity |
| `Intent.setData()` | Set URI/data for an Intent |
| `Intent.setType()` | Set MIME type |
| `Uri.parse()` | Convert a URI string into a `Uri` |
| `startActivity()` | Start another Activity |
| `ActivityResultContracts` | Handle Activity results |

---

# 🔐 Permission Handling

Some Android operations require permissions.

Permissions can be declared in the `AndroidManifest.xml`.

Example:

```xml
<uses-permission android:name="android.permission.CAMERA" />
```

Before requesting a permission, it can be checked using:

```kotlin
ContextCompat.checkSelfPermission()
```

If permission is not granted, it can be requested using:

```kotlin
ActivityCompat.requestPermissions()
```

> **Note:** The exact permissions required depend on the Android operation and the Android version being used.

---

# 📱 Suggested User Interface

The main screen can contain buttons such as:

```text
--------------------------------
|       Intent Demonstration   |
|                              |
|      [ Make Call ]           |
|      [ Open URL ]            |
|      [ Call Log ]            |
|      [ Open Gallery ]        |
|      [ Set Alarm ]           |
|      [ Open Camera ]         |
|      [ Login Activity ]      |
|                              |
--------------------------------
```

Each button performs its corresponding Intent operation.

---

# 📂 Suggested Project Structure

```text
Practical-3/
│
├── README.md
│
└── app/
    └── src/
        └── main/
            ├── java/
            │   └── com.example.practical3/
            │       ├── MainActivity.kt
            │       └── LoginActivity.kt
            │
            ├── res/
            │   ├── drawable/
            │   ├── layout/
            │   │   ├── activity_main.xml
            │   │   └── activity_login.xml
            │   └── values/
            │
            └── AndroidManifest.xml
```

---

# ▶️ How to Run

1. Open **Android Studio**.
2. Create or open the Practical-3 Android project.
3. Select **Kotlin** as the programming language.
4. Create the required Activities.
5. Design the main screen using `ConstraintLayout`.
6. Add buttons for each operation.
7. Implement the required Intent code in `MainActivity.kt`.
8. Add required permissions to `AndroidManifest.xml`.
9. Connect an Android device or start an Android Emulator.
10. Run the application.
11. Test each button individually.

---

# 🧪 Testing

The application should be tested for the following operations:

| Test | Expected Result |
|---|---|
| Make Call | Phone dialer opens with specified number |
| Open URL | Website opens in browser |
| Call Log | Call history opens |
| Gallery | Gallery/image picker opens |
| Set Alarm | Alarm screen opens |
| Camera | Camera application opens |
| Login Activity | Login Activity opens |

---

# 📸 Application Screenshots

Add screenshots of your application here after completing the practical.

```text
### Main Screen
[Add screenshot here]

### Call Intent
[Add screenshot here]

### URL Intent
[Add screenshot here]

### Gallery
[Add screenshot here]

### Alarm
[Add screenshot here]

### Camera
[Add screenshot here]

### Login Activity
[Add screenshot here]
```

---

# 🧠 Key Learning Outcomes

After completing this practical, we understand:

- How Android Intents work.
- Difference between implicit and explicit intents.
- How to open other Android applications.
- How to pass data using Intent.
- How to use `Uri.parse()`.
- How to use `setData()` and `setType()`.
- How to start another Activity.
- How Android permissions are handled.
- How to use Activity Result APIs.
- How different Android components communicate with each other.

---

# ✅ Conclusion

This practical demonstrates the implementation of **Implicit and Explicit Intents** in an Android application using Kotlin. It shows how an Android application can interact with other applications and Activities for tasks such as making calls, opening websites, accessing the call log and gallery, setting alarms, opening the camera, and navigating to another Activity.
