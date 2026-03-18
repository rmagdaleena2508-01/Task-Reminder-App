# Task Reminder App 📝✨

A console-based Task Reminder application built with **Dart** to demonstrate asynchronous programming concepts including `Future`, `async`, and `await`, with **task completion tracking**.

## 📋 Project Overview

This mini project is developed as part of an App Development course, focusing on Dart fundamentals and asynchronous programming patterns essential for modern mobile application development.

The application simulates real-world scenarios where apps interact with remote servers or databases through delayed asynchronous operations.

## ✨ Features

### 1. **Task Model**
- Custom `Task` class with properties:
  - **Title**: Name of the task
  - **Description**: Detailed information about the task
  - **Due Date**: Deadline for task completion
  - **Completion Status**: Track if task is completed or pending
- Object-oriented design with constructors and methods

### 2. **Asynchronous Task Loading**
- Simulates fetching tasks from a database/API
- Uses `Future.delayed()` with 3-second delay
- Implements `async` and `await` keywords
- Includes error handling with try-catch blocks

### 3. **Add New Task**
- Asynchronous function to create and save new tasks
- Simulates network delay for save operation
- User input validation
- Dynamic task list management

### 4. **Task Display Logic**
- Display all tasks after asynchronous loading
- View detailed information for individual tasks
- Proper execution flow using await
- Real-time task list updates

### 5. **🆕 Task Completion Feature**
- Mark tasks as completed with async operation
- Separate tracking for pending and completed tasks
- Completed tasks moved to dedicated list
- Completed tasks removed from active/current tasks view
- 3-second delay simulation for database update

### 6. **View Completed Tasks**
- Dedicated menu option to view all completed tasks
- Shows completion status with visual indicators (✅)
- Displays total count of completed tasks
- Async loading with 2-second delay

### 7. **Interactive Menu System**
- User-friendly console interface
- 7 menu options:
  1. Load all tasks from "database"
  2. Add new custom tasks
  3. View specific task details
  4. **Display current (pending) tasks only**
  5. **Mark task as done** ⭐ NEW
  6. **View completed tasks** ⭐ NEW
  7. Exit application with summary

## 🎯 Learning Objectives

This project demonstrates:
- ✅ Dart language fundamentals (variables, functions, classes, lists)
- ✅ Future and asynchronous operations
- ✅ async and await keywords usage
- ✅ Error handling in asynchronous code
- ✅ Real-world application logic simulation
- ✅ Clean and modular code structure
- ✅ State management with multiple lists
- ✅ Boolean flags for tracking status

## 🚀 How to Run

### Prerequisites
- Dart SDK installed on your system
- Basic understanding of command line/terminal

### Steps

1. **Clone this repository**
   ```bash
   git clone <your-repository-url>
   cd task-reminder-app
   ```

2. **Run the application**
   ```bash
   dart task_reminder_app_with_completion.dart
   ```

3. **Follow the on-screen menu**
   - Choose option 1 to load sample tasks
   - Choose option 2 to add your own tasks
   - Choose option 3 to view task details
   - Choose option 4 to see current pending tasks
   - Choose option 5 to mark tasks as done ⭐
   - Choose option 6 to view completed tasks ⭐
   - Choose option 7 to exit

## 📦 Project Structure

```
task-reminder-app/
│
├── task_reminder_app_with_completion.dart    # Enhanced main application
├── README.md                                  # Project documentation
└── GitHub_Link.txt                           # Repository URL
```

## Screenshots
<img width="2022" height="1334" alt="Screenshot 2026-03-18 221018" src="https://github.com/user-attachments/assets/6d109540-7ed8-4a97-b12e-56d341ef6d65" />
<img width="2047" height="1323" alt="Screenshot 2026-03-18 221048" src="https://github.com/user-attachments/assets/41aa4b6d-e837-4465-8917-bcd25e0dd8e3" />
<img width="2045" height="1265" alt="Screenshot 2026-03-18 221059" src="https://github.com/user-attachments/assets/df53276a-5c6f-4f29-886a-58af5ae19aa5" />


## 💻 Core Concepts Covered

### Dart Basics
- Variables and data types
- Functions and methods
- Classes and objects
- Lists and collections
- Boolean properties
- User input/output

### Asynchronous Programming
- `Future<T>` type
- `async` function modifier
- `await` keyword
- `Future.delayed()` for simulation
- Try-catch error handling

### State Management
- Multiple list management
- Task status tracking
- Dynamic list operations (add, remove)

## 🔧 Technical Implementation

### Task Class Enhancement
```dart
class Task {
  String title;
  String description;
  DateTime dueDate;
  bool isCompleted;  // NEW: Track completion status
  
  Task({
    required this.title,
    required this.description,
    required this.dueDate,
    this.isCompleted = false,  // Default to pending
  });
}
```

### Dual List System
```dart
List<Task> taskList = [];           // Pending tasks
List<Task> completedTaskList = [];  // Completed tasks
```

### Mark Task as Completed (Async)
```dart
Future<void> markTaskAsCompleted(int taskIndex) async {
  await Future.delayed(Duration(seconds: 3));  // Simulate DB update
  
  Task taskToComplete = taskList[taskIndex];
  taskToComplete.isCompleted = true;
  
  completedTaskList.add(taskToComplete);  // Add to completed
  taskList.removeAt(taskIndex);            // Remove from pending
}
```

### Sample Tasks
The application comes with 5 pre-loaded sample tasks:
1. Complete Dart Assignment
2. Study Flutter Basics
3. Attend App Development Class
4. Submit GitHub Repository
5. Prepare Project Documentation

### Asynchronous Operations
All I/O operations simulate real-world delays:
- **Fetch tasks**: 3-second delay
- **Add task**: 3-second delay
- **Mark as completed**: 3-second delay
- **View details**: 2-second delay
- **View completed tasks**: 2-second delay

## 📸 Example User Flow

```
1. User loads tasks (Option 1)
   → 5 pending tasks displayed

2. User marks task #1 as done (Option 5)
   → Task moves to completed list
   
3. User views current tasks (Option 4)
   → Only 4 pending tasks shown
   
4. User views completed tasks (Option 6)
   → Shows 1 completed task with ✅ indicator
   
5. User exits (Option 7)
   → Summary: 4 pending, 1 completed
```

## 🎨 Visual Indicators

- **⏳** - Pending/Active task
- **✅** - Completed task
- **❌** - Error message
- **📊** - Statistics/Summary

## 📝 Code Highlights

### Error Handling
```dart
try {
  await markTaskAsCompleted(taskNum - 1);
} catch (e) {
  print('❌ Error marking task as completed: $e');
}
```

### Task Status Display
```dart
@override
String toString() {
  String status = isCompleted ? '✅' : '⏳';
  return '$status Task: $title | Due: ${dueDate.day}/${dueDate.month}/${dueDate.year}';
}
```

## 🎓 Skills Demonstrated

- Understanding of Dart language fundamentals
- Ability to write and manage asynchronous code
- Real-world problem-solving for app development
- State management with multiple data structures
- Clean code practices and documentation
- Version control with Git/GitHub
- Boolean logic for status tracking
- List manipulation (add, remove, iterate)
- Readiness for Flutter and mobile development

## 📚 Real-World Use Case

Modern mobile applications constantly interact with:
- Remote APIs
- Cloud databases
- Local storage
- Network requests
- User state management

This project simulates such scenarios with added complexity of tracking task completion status, mirroring real-world to-do apps like:
- Google Tasks
- Microsoft To-Do
- Todoist
- Any.do

## 🆕 Enhanced Features Summary

| Feature | Description | Async Operation |
|---------|-------------|-----------------|
| **Load Tasks** | Fetch from "database" | 3 seconds |
| **Add Task** | Save new task | 3 seconds |
| **View Details** | Load task info | 2 seconds |
| **Display Current** | Show pending only | Instant |
| **Mark as Done** | Complete task | 3 seconds |
| **View Completed** | Show completed | 2 seconds |

## 🤝 Contributing

This is an educational project. Feedback and suggestions are welcome!

## 👨‍💻 Author

**MAGDALEENA R**  
App Development Course Mini Project  
**SRM Institute Of Science and Technology,Vadapalani Campus**

## 📄 License

This project is created for educational purposes as part of an App Development course.

---

### 🌟 Key Takeaways

- Asynchronous programming is essential for modern app development
- `async`/`await` makes asynchronous code readable and maintainable
- Dart's Future API enables non-blocking operations
- Proper error handling ensures robust applications
- State management is crucial for tracking user actions
- Clean code structure improves maintainability
- Boolean flags enable simple status tracking
- List operations are fundamental to data management

---

**Note**: This is a console-based application focusing on backend logic and asynchronous programming concepts. UI implementation is intentionally excluded to emphasize core Dart fundamentals and state management.


