# 🎯 Flutter Todo App with BLoC Pattern
A minimalist Flutter todo list that leverages `flutter_bloc` for state management and `hydrated_bloc` for automatic local persistence. Swipe to delete, check off tasks, and trust that your list survives app restarts without extra wiring.

## ✳️ Visual Overview 

https://github.com/user-attachments/assets/bf04e0a4-5ea5-461d-ae6a-131551b4900d


## 📹 Demo
First, see it in action:
1. Clone the repo and open in your editor.
2. Run.
```bash
flutter pub get
flutter run
```
3. 	Tap the “+” FAB, enter a title and description, then save.
4. 	Swipe a task card to reveal the Delete button.
5. 	Check or uncheck the box to mark a task done/undone.
6. 	Close and relaunch the app—your tasks and their states reappear automatically.


## 🔍 Project Overview

### Problem
- Users need a simple, offline-capable task manager that feels snappy and reliable, with a clear separation between UI and business logic.

### Key Components
- flutter_bloc: BLoC pattern for event→state handling.
- hydrated_bloc: Automatic JSON serialization to disk.
- flutter_slidable: Swipe-to-delete UI affordance.
- Equatable: Value-based comparison for BLoC events and states.
- AlertDialog + TextField: Quick task creation form.


## 🛠️ Getting Started
1. Clone the repository:
```bash
git clone https://github.com/ex-rnd/Flutter-Todo-App-Bloc-With-Hydrate.git
cd soulful-todo
```

2. Install dependencies:
```bash
flutter pub get
```

3. Launch on an emulator or device:
```bash
flutter run
```


## ▶️ Usage
### Add a task:
- Tap the yellow FAB, fill in title & description, tap the check icon.
### Delete a task:
- Swipe a card to the left and tap Delete.
### Toggle completion:
- Tap the checkbox on any task.
### Persistence:
- Tasks and their done/undone status auto-reload on every app launch.


## 📐 App Architecture

### High level flow
```md
HomeScreen 
  ├─ FAB → showDialog → AddTodo event
  ├─ BlocBuilder<TodoBloc,TodoState>
      └─ ListView of Task Cards
           ├─ Slidable → RemoveTodo event
           └─ Checkbox → AlterTodo event
TodoBloc
  ├─ on<AddTodo>    → inserts new task at index 0
  ├─ on<RemoveTodo> → filters out a task
  ├─ on<AlterTodo>  → toggles isDone on a cloned list
  └─ hydrated toJson/fromJson for disk storage 
```


## 🤝 Contributing
- Fork the repo
- Branch naming: feature/xyz or fix/xyz
- Follow Dart formatting:
```bash
flutter format .
```
- Commit messages should be clear and reference any related issue.
- Submit PRs with clear descriptions and link related issues


### 🎮 Thank you for exploring Flutter Todo App with BLoC/Hydrate, an offline-first, BLoC-driven app! 🎉!





