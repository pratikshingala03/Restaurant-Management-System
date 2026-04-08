# Restaurant-Management-System
# Restaurant Management System – Project Report

---

## 1. Introduction

The chosen organization for this project is a **restaurant**, where daily operations involve managing menu items, customers, orders, and billing. In many small or local restaurants, these tasks are often handled manually, which can lead to inefficiencies, errors, and difficulty in tracking records.

The purpose of this software is to provide a **simple command-line based Restaurant Management System** that digitizes these operations. The system allows staff to manage menu items, register customers, place orders, and generate bills efficiently.

The scope of the program includes:

* Managing menu items and their availability
* Registering and viewing customers
* Placing and tracking orders
* Generating and paying bills

This system is designed to be simple, user-friendly, and suitable for small-scale restaurant operations.

---

## 2. System Design

The system follows a **modular and object-oriented design**, where different components are separated into individual classes and files.

### Main Classes

* **MenuItem**

  * Stores item details such as name, category, price, and availability
* **Customer**

  * Stores customer information (ID, name, phone)
* **Order**

  * Represents a customer order containing multiple menu items
  * Tracks order status (e.g., pending, served)
* **Bill**

  * Handles billing for orders, including total calculation and payment status

### Relationships

* A **Customer** can have multiple **Orders**
* An **Order** contains multiple **MenuItems**
* A **Bill** is generated for one **Order**

### Data Management

Data is managed using:

* **Dictionaries** (in-memory storage)
* **File handling (via `data_manager.py`)** to save and load data

Unique IDs are generated using a helper function (`next_id`) to ensure consistency across:

* Menu items (M001, M002, …)
* Customers (C001, C002, …)
* Orders (O001, O002, …)
* Bills (B001, B002, …)

---

## 3. Implementation Overview

The system is implemented using core Python concepts:

### Functions

* Each feature (e.g., add customer, place order) is implemented as a separate function
* Improves readability and reusability

### Classes and Objects

* Object-Oriented Programming is used to model real-world entities
* Each class encapsulates related data and behavior

### Exception Handling

* `try-except` blocks are used to handle invalid user input
* Prevents program crashes and improves user experience

### Modularity

* Code is divided into multiple files:

  * `menu.py`, `customer.py`, `order.py`, `bill.py`, `data_manager.py`
* Each file has a clear responsibility

### Readability

* Clear function names (e.g., `add_customer`, `place_order`)
* Structured menu interface
* Use of comments and simple logic

---

## 4. Testing and Demonstration

The program was tested using multiple scenarios to ensure correctness.

### Example Usage

**Placing an Order:**

* User selects option to place an order
* Enters customer ID
* Adds items by entering item IDs
* Finalizes order

**Generating a Bill:**

* User selects an unbilled order
* Optionally applies a discount
* System calculates total and prints bill

### Error Handling Examples

* Invalid menu item ID:
  → Displays: `[Error] Item ID not found.`

* Empty order:
  → Displays: `[Error] Cannot place an empty order.`

* Invalid discount input:
  → Displays warning and continues without discount

### Testing Approach

* Manual testing with different inputs
* Tested edge cases such as:

  * Empty data
  * Invalid IDs
  * Incorrect numeric inputs

---

## 5. Reflection

### Challenges Faced

* Designing relationships between classes (Order, Customer, Bill)
* Managing data persistence using file handling
* Ensuring user input validation without making the code too complex

### Lessons Learned

* Importance of modular programming
* Practical use of Object-Oriented Programming concepts
* Handling real-world scenarios like invalid input and edge cases

### Future Improvements

* Add database support (e.g., SQLite)
* Develop a graphical user interface (GUI)
* Implement a web-based version
* Add user authentication and roles (admin/staff)
* Improve data persistence across sessions

---

## Conclusion

This project successfully demonstrates a functional Restaurant Management System using Python. It applies key programming concepts such as OOP, modularity, and error handling, while solving a real-world problem in a structured and efficient way.
