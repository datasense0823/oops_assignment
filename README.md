# 📘 Python OOP Assignment – Build a Library Management System

## 👋 Introduction

In this assignment, you will apply the concepts of Object-Oriented Programming (OOP) in Python to create a basic **Library Management System**. 

The purpose of this exercise is to help you understand how real-world entities can be modeled using classes and objects. You will create two classes — one for individual books, and another for the overall library that manages those books.

This assignment will specifically test your understanding of:
- Creating classes in Python
- Using the `__init__()` constructor to initialize objects
- Proper use of the `self` keyword
- Writing and using instance methods

---

## 🎯 Objective

You need to design two classes:

### 1. `Book` class – represents a single book.
### 2. `Library` class – represents a collection of books and provides functionality to manage them.

Each class must be thoughtfully designed, and the interaction between them should reflect how a real library works.

---

## 🧱 Part 1: Create the `Book` Class

Every book in a library has some basic information. Start by creating a class called `Book` with the following:

### Attributes (what data should a book have?)
- `title` – The name of the book
- `author` – Who wrote the book
- `isbn` – A unique identifier for the book
- `available` – A boolean value indicating if the book is currently available (`True`) or borrowed (`False`)

### Methods (what actions can a book perform?)
- `__init__(self, title, author, isbn, available)` – Constructor method that initializes the book with the values mentioned above
- `display_info(self)` – Print the book's details in a neat format
- `mark_unavailable(self)` – Change the availability status to `False`
- `mark_available(self)` – Change the availability status to `True`

---

## 🏛️ Part 2: Create the `Library` Class

Now that we can represent individual books, let’s create a class that manages a collection of books.

### Attributes:
- `book_list` – A list that will store all `Book` objects added to the library

### Methods:
- `__init__(self)` – Initialize `book_list` as an empty list
- `add_book(self, book)` – Takes a `Book` object and adds it to `book_list`
- `remove_book(self, isbn)` – Removes a book based on its ISBN
- `borrow_book(self, isbn)` – If the book is available, mark it as unavailable
- `return_book(self, isbn)` – Mark the book as available again
- `display_books(self)` – Print the details of all books currently in the library

---

## 🧪 Example Test Run

Here’s an example of how your classes might be used:

```python
book1 = Book("Harry Potter", "J.K. Rowling", "12345", True)
book2 = Book("To Kill a Mockingbird", "Harper Lee", "67890", True)

library = Library()

library.add_book(book1)
library.add_book(book2)

print("Initial Book List:")
library.display_books()

library.borrow_book("12345")
print("\nAfter Borrowing Harry Potter:")
library.display_books()

library.return_book("12345")
print("\nAfter Returning Harry Potter:")
library.display_books()

library.remove_book("67890")
print("\nAfter Removing To Kill a Mockingbird:")
library.display_books()
