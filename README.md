# Student Grade Tracker

A simple and clean Flutter application built as a course project to demonstrate core mobile app development concepts. The app features an intro welcome screen and a login screen with form validation.

---

## App Overview

The app consists of **two screens**:

1. **Intro Screen** — A welcome page with the app name, feature highlights, and a "Get Started" button that navigates to the login screen.
2. **Login Screen** — A form-based login page with email and password fields, input validation, password visibility toggle, and credential verification.

### Demo Credentials

| Email | Password |
|---|---|
| admin@university.edu | admin123 |

---

## Screenshots

| Intro Screen | Login Screen | Validation |
|---|---|---|
| ![Intro](screenshots/intro.png) | ![Login](screenshots/login.png) | ![Validation](screenshots/validation.png) |

> Add your own screenshots by creating a `screenshots/` folder in the root of the project.

---

## Project Structure

```
lib/
├── main.dart                  # App entry point - MaterialApp setup
└── screens/
    ├── intro_screen.dart      # Welcome screen (StatelessWidget)
    └── login_screen.dart      # Login screen (StatefulWidget)
```

---

## Flutter Concepts Used

### Widgets

| Widget | Where Used | Purpose |
|---|---|---|
| `Scaffold` | Both screens | Base page structure |
| `AppBar` | Login screen | Top bar with title and back button |
| `Column` | Both screens | Vertical arrangement of elements |
| `Row` | Both screens | Horizontal arrangement (icon + text pairs) |
| `Container` | Both screens | Styling with padding, color, and border radius |
| `Text` | Both screens | Displaying titles, labels, and hints |
| `Icon` | Both screens | Visual icons (school, email, lock, etc.) |
| `SizedBox` | Both screens | Adding spacing between widgets |
| `Padding` | Both screens | Adding padding around widgets |
| `ElevatedButton` | Both screens | "Get Started" and "Login" buttons |
| `TextFormField` | Login screen | Email and password input fields |
| `IconButton` | Login screen | Password visibility toggle |
| `SingleChildScrollView` | Both screens | Makes content scrollable |
| `SnackBar` | Login screen | Success and error messages |

### Core Concepts

| Concept | Where Used | What It Does |
|---|---|---|
| `StatelessWidget` | Intro screen | Screen with no changing state |
| `StatefulWidget` | Login screen | Screen with state that changes (password toggle) |
| `setState()` | Login screen | Toggles password visibility on/off |
| `Navigator.push()` | Intro screen | Navigates forward from intro to login |
| `Navigator.pop()` | Login screen | Navigates back from login to intro |
| `MaterialPageRoute` | Intro screen | Defines the route for navigation |
| `Form` | Login screen | Wraps input fields for validation |
| `GlobalKey<FormState>` | Login screen | Key to trigger form validation |
| `TextEditingController` | Login screen | Reads text from email and password fields |
| `validator` | Login screen | Checks if email and password are valid |
| `obscureText` | Login screen | Hides password characters |
| `BoxDecoration` | Both screens | Adds rounded corners, background color |
| `BorderRadius` | Both screens | Rounds corners on containers and buttons |
| `ScaffoldMessenger` | Login screen | Shows SnackBar messages |

---

## App Flow

```
main.dart
  └── MyApp (StatelessWidget)
        └── MaterialApp
              └── IntroScreen (StatelessWidget)
                    │
                    │  [User taps "Get Started"]
                    │  Navigator.push()
                    ▼
              LoginScreen (StatefulWidget)
                    │
                    │  [User taps back arrow]
                    │  Navigator.pop()
                    ▼
              IntroScreen
```

---

## How to Run

### Prerequisites

- Flutter SDK installed ([flutter.dev/docs/get-started/install](https://flutter.dev/docs/get-started/install))
- VS Code with Flutter extension (or Android Studio)
- An emulator or physical device

### Steps

1. **Create the project**
   ```bash
   flutter create student_tracker
   cd student_tracker
   ```

2. **Replace the `lib/` folder** with the files from this repository

3. **Run the app**
   ```bash
   flutter run
   ```
   Or press **F5** in VS Code.

---

## Validation Rules

### Email Field
- Cannot be empty → shows "Please enter your email"
- Must contain `@` → shows "Please enter a valid email"

### Password Field
- Cannot be empty → shows "Please enter your password"
- Must be at least 6 characters → shows "Password must be at least 6 characters"

---

## Built With

- **Flutter** — UI framework
- **Dart** — Programming language
- **Material Design** — Widget library
- **VS Code** — Development environment

---

## Future Enhancements

- Add a registration screen
- Connect login to a grade dashboard with SGPA/CGPA calculation
- Add default student data for multiple semesters
- Implement persistent storage for user accounts

---

## Author

Built as a course project for App Development.

---

## License

This project is for educational purposes.
