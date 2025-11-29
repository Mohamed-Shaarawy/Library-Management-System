# Library Management System

A Java-based **Library Management System** that helps manage books, users/members, and borrowing/returning operations.  
This project is intended as a learning project for Database Course.

## ✨ Features

- **Book Management**
  - Add new books (title, author, ISBN, category, publication year, etc.)
  - Update book information
  - Remove books from the catalog
  - Search books by title, author, ISBN, or category
  - Track availability status (available / borrowed)

- **Member/User Management**
  - Add new members
  - Update member details
  - Deactivate/remove members
  - Search members by name, ID, or contact info

- **Borrowing & Returning**
  - Issue a book to a member
  - Record return of books
  - Calculate and track due dates
  - (Optional) Calculate late fees / penalties

- **Reports & Queries** (if implemented)
  - List all available books
  - List currently borrowed books
  - List overdue books
  - Member borrowing history

- **Persistence** (update to match your implementation)
  - In-memory data structures **or**
  - File-based storage (e.g., text/CSV/JSON/serialized objects) **or**
  - Database (JDBC, MySQL/PostgreSQL, etc.)

- **User Interface**
  - Console/CLI-based menu **or**
  - Swing/JavaFX GUI (windows, forms, tables, etc.)

---

## 🧱 Project Structure

```text
Library-Management-System/
├─ src/
│  └─ main/
│     └─ java/
│        └─ com/example/library/
│           ├─ Main.java
│           ├─ model/
│           │  ├─ Book.java
│           │  ├─ Member.java
│           │  └─ Loan.java
│           ├─ service/
│           │  ├─ LibraryService.java
│           │  └─ FineCalculator.java
│           ├─ repository/
│           │  ├─ BookRepository.java
│           │  └─ MemberRepository.java
│           └─ ui/
│              ├─ ConsoleUI.java
│              └─ Menu.java
├─ README.md
└─ (build files: pom.xml or build.gradle, etc.)
```
### Main Components

- **`Main` / Application Entry Point**
  - Contains the `public static void main(String[] args)` method.
  - Initializes services, repositories, and launches the UI (console or GUI).

- **Model Layer (`model/`)**
  - `Book` – fields like `id`, `title`, `author`, `isbn`, `category`, `year`, `available`.
  - `Member` – fields like `id`, `name`, `email`, `phone`, `membershipDate`.
  - `Loan` / `BorrowRecord` – fields like `book`, `member`, `borrowDate`, `dueDate`, `returnDate`.

- **Service Layer (`service/`)**
  - `LibraryService` – core business logic:
    - add/update/remove/search books
    - register/update/search members
    - issue & return books
    - check availability and constraints
  - `FineCalculator` (optional) – late fee calculations.

- **Repository/Data Layer (`repository/`)**
  - Handles data persistence:
    - In-memory collections (e.g., `List`, `Map`) **or**
    - File reading/writing **or**
    - Database using JDBC/ORM.

- **User Interface (`ui/`)**
  - `ConsoleUI` / `Menu` – displays menus, reads user input, and calls service methods.
  - If GUI-based, classes for windows, dialogs, and forms.

---

## 🚀 Getting Started

### Prerequisites

- **Java**: JDK 8+ (recommend JDK 11 or later)
- (If using a build tool, mention it:)
  - **Maven** or **Gradle** (optional but recommended)

### Clone the Repository

```bash
git clone https://github.com/Mohamed-Shaarawy/Library-Management-System.git
cd Library-Management-System
```

### Build & Run

Adjust one of the following to match your project:

#### Option 1: Plain `javac` / `java`

If your sources are under `src` and there’s a `Main` class:

```bash
# From project root
javac -d out $(find src -name "*.java")
java -cp out com.example.library.Main
```

Replace `com.example.library.Main` with your actual fully qualified main class.

#### Option 2: Maven

If you have a `pom.xml`:

```bash
mvn clean compile
mvn exec:java -Dexec.mainClass="com.example.library.Main"
```

#### Option 3: Gradle

If you have a `build.gradle`:

```bash
./gradlew build
./gradlew run
```

---

## 🧑‍💻 Usage

This will depend on your UI; here are example flows.

### Console/CLI Version

1. Run the application (see **Build & Run**).
2. You should see a menu like:

   ```
   ==== Library Management System ====
   1. Add Book
   2. List Books
   3. Register Member
   4. Issue Book
   5. Return Book
   0. Exit
   ```

3. Enter the number of the operation you want.
4. Follow the prompts to enter book/member/loan details.
5. Data will be persisted according to your implementation (in memory, file, or DB).

### GUI Version 

- Launch the application; a main window should open with:
  - Menus or tabs for **Books**, **Members**, **Borrowing**, **Reports**.
  - Forms to add/edit records.
  - Tables for listing books, members, and loans.


## 📦 Data Persistence

Describe your actual persistence layer. For example:

- **In-Memory Only**
  - All data is stored in Java collections and lost when the application stops.

- **File-Based Storage**
  - Data is saved to a locally hosted DB server using MyPhpAdmin.

- **Database (JDBC)**
  - Uses a relational database (e.g., MySQL) with tables:
    - `books`, `members`, `loans`, etc.
  - Configuration options (URL, username, password) are in a config file or environment variables.

Include any configuration instructions (e.g., `application.properties`, `.env`, etc.).


## 🗺️ Roadmap / Possible Enhancements

- User authentication & roles (admin vs. librarian vs. member)
- Web interface (Spring Boot, REST API, or similar)
- Better reporting & export (CSV/PDF)
- Notifications for overdue books (email/SMS)
- Support for reservations/holds
- Multi-branch library support



## 📝 License
This project is **for educational purposes only**
