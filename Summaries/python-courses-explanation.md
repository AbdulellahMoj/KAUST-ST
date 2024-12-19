# Python Programming: A Comprehensive Guide

## Course 1: Python Basics

### Module 1: General Introduction

#### 1.1 Values and Data Types
Python has several basic data types:
```python
# Numbers
integer_number = 42
float_number = 3.14

# Strings
text = "Hello, World!"
multiline_text = """This is a
multiline string"""

# Boolean
is_true = True
is_false = False

# Type checking
print(type(integer_number))  # <class 'int'>
print(type(text))           # <class 'str'>
```

#### 1.2 Turtle Graphics
The Turtle module provides a way to learn programming through visual feedback:
```python
import turtle

# Create a turtle instance
t = turtle.Turtle()

# Draw a square
for _ in range(4):
    t.forward(100)  # Move forward 100 units
    t.right(90)     # Turn right 90 degrees

# Draw a star
for _ in range(5):
    t.forward(100)
    t.right(144)

turtle.done()  # Keep the window open
```

### Module 2: Sequences and Iteration

#### 2.1 Lists and Strings Operations
```python
# List operations
numbers = [1, 2, 3, 4, 5]
print(numbers[0])      # First element: 1
print(numbers[-1])     # Last element: 5
print(numbers[1:4])    # Slicing: [2, 3, 4]

# String operations
text = "Python"
print(text[0])        # First character: 'P'
print(text[::-1])     # Reverse string: 'nohtyP'
print(len(text))      # Length: 6
```

#### 2.2 The Accumulator Pattern
```python
# Sum accumulator
numbers = [1, 2, 3, 4, 5]
total = 0
for num in numbers:
    total += num
print(f"Sum: {total}")  # Sum: 15

# String accumulator
words = ["Hello", "World", "!"]
sentence = ""
for word in words:
    sentence += word + " "
print(sentence.strip())  # Hello World !
```

### Module 3: Booleans and Conditionals

#### 3.1 Boolean Expressions
```python
# Comparison operators
x = 5
y = 10
print(x < y)    # True
print(x == y)   # False
print(x >= 3)   # True

# Logical operators
a = True
b = False
print(a and b)  # False
print(a or b)   # True
print(not a)    # False
```

#### 3.2 Conditional Statements
```python
# If-elif-else structure
score = 85

if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
else:
    grade = "F"

print(f"Grade: {grade}")  # Grade: B
```

## Course 2: Functions, Files, and Dictionaries

### Module 1: Files and CSV

#### 1.1 File Operations
```python
# Writing to a file
with open("example.txt", "w") as file:
    file.write("Hello, World!\n")
    file.write("This is a test file.")

# Reading from a file
with open("example.txt", "r") as file:
    content = file.read()
    print(content)

# Reading CSV
import csv

with open("data.csv", "w") as file:
    writer = csv.writer(file)
    writer.writerow(["Name", "Age"])
    writer.writerow(["Alice", 25])
    writer.writerow(["Bob", 30])

with open("data.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)
```

### Module 2: Dictionaries

#### 2.1 Dictionary Operations
```python
# Creating and accessing dictionaries
student = {
    "name": "Alice",
    "age": 20,
    "grades": [85, 90, 88]
}

print(student["name"])  # Alice
print(student.get("age"))  # 20

# Dictionary methods
print(student.keys())    # dict_keys(['name', 'age', 'grades'])
print(student.values())  # dict_values(['Alice', 20, [85, 90, 88]])
print(student.items())   # dict_items([('name', 'Alice'), ('age', 20), ('grades', [85, 90, 88])])
```

#### 2.2 Dictionary Accumulation
```python
# Counting word frequency
text = "the quick brown fox jumps over the lazy dog"
word_count = {}

for word in text.split():
    word_count[word] = word_count.get(word, 0) + 1

print(word_count)  # {'the': 2, 'quick': 1, 'brown': 1, ...}
```

### Module 3: Functions

#### 3.1 Function Definition and Parameters
```python
# Basic function
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))  # Hello, Alice!

# Default parameters
def power(base, exponent=2):
    return base ** exponent

print(power(3))     # 9 (3^2)
print(power(2, 3))  # 8 (2^3)

# Multiple return values using tuple
def calculate_statistics(numbers):
    return min(numbers), max(numbers), sum(numbers)/len(numbers)

min_val, max_val, avg = calculate_statistics([1, 2, 3, 4, 5])
print(f"Min: {min_val}, Max: {max_val}, Average: {avg}")
```

## Course 3: Data Collection and Processing

### Module 1: Nested Data and Iteration

#### 1.1 Working with JSON
```python
import json

# Creating nested data
data = {
    "name": "Alice",
    "age": 20,
    "courses": [
        {"name": "Python", "grade": 90},
        {"name": "Java", "grade": 85}
    ]
}

# Converting to JSON
json_string = json.dumps(data, indent=2)
print(json_string)

# Parsing JSON
parsed_data = json.loads(json_string)
print(parsed_data["courses"][0]["grade"])  # 90
```

#### 1.2 Nested Iteration
```python
# Processing nested structures
students = [
    {"name": "Alice", "grades": [90, 85, 88]},
    {"name": "Bob", "grades": [92, 88, 85]},
    {"name": "Charlie", "grades": [78, 85, 90]}
]

# Calculate average grade for each student
for student in students:
    grades = student["grades"]
    average = sum(grades) / len(grades)
    print(f"{student['name']}: {average:.2f}")
```

### Module 2: Advanced Accumulation

#### 2.1 List Comprehensions
```python
# Basic list comprehension
numbers = [1, 2, 3, 4, 5]
squares = [n ** 2 for n in numbers]
print(squares)  # [1, 4, 9, 16, 25]

# Filtered list comprehension
even_squares = [n ** 2 for n in numbers if n % 2 == 0]
print(even_squares)  # [4, 16]

# Nested list comprehension
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flattened = [num for row in matrix for num in row]
print(flattened)  # [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

## Course 4: Classes and Inheritance

### Module 1: Classes

#### 1.1 Class Definition and Methods
```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        self.grades = []
    
    def add_grade(self, grade):
        self.grades.append(grade)
    
    def get_average(self):
        if not self.grades:
            return 0
        return sum(self.grades) / len(self.grades)
    
    def __str__(self):
        return f"Student(name={self.name}, age={self.age})"

# Creating instances
student = Student("Alice", 20)
student.add_grade(90)
student.add_grade(85)
print(student.get_average())  # 87.5
print(student)  # Student(name=Alice, age=20)
```

### Module 2: Inheritance

#### 2.1 Class Inheritance
```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def introduce(self):
        return f"My name is {self.name} and I'm {self.age} years old"

class Student(Person):
    def __init__(self, name, age, student_id):
        super().__init__(name, age)
        self.student_id = student_id
        self.courses = []
    
    def enroll(self, course):
        self.courses.append(course)
    
    def introduce(self):
        return f"{super().introduce()} and my student ID is {self.student_id}"

# Using inheritance
student = Student("Alice", 20, "A12345")
print(student.introduce())
student.enroll("Python Programming")
print(f"Courses: {student.courses}")
```

### Module 3: Unit Testing and Exceptions

#### 3.1 Unit Testing
```python
import unittest

class Calculator:
    def add(self, x, y):
        return x + y
    
    def divide(self, x, y):
        if y == 0:
            raise ValueError("Cannot divide by zero")
        return x / y

class TestCalculator(unittest.TestCase):
    def setUp(self):
        self.calc = Calculator()
    
    def test_add(self):
        self.assertEqual(self.calc.add(3, 5), 8)
        self.assertEqual(self.calc.add(-1, 1), 0)
    
    def test_divide(self):
        self.assertEqual(self.calc.divide(10, 2), 5)
        with self.assertRaises(ValueError):
            self.calc.divide(10, 0)

if __name__ == '__main__':
    unittest.main()
```

#### 3.2 Exception Handling
```python
def safe_divide(x, y):
    try:
        result = x / y
    except ZeroDivisionError:
        print("Error: Division by zero!")
        result = None
    except TypeError:
        print("Error: Invalid operand types!")
        result = None
    else:
        print("Division successful!")
    finally:
        print("Execution completed")
    return result

# Testing exception handling
print(safe_divide(10, 2))   # Normal case
print(safe_divide(10, 0))   # Division by zero
print(safe_divide("10", 2)) # Type error
```

## Best Practices and Tips

1. **Code Organization**
   - Use meaningful variable and function names
   - Follow PEP 8 style guidelines
   - Keep functions and classes focused on single responsibilities

2. **Debugging**
   - Use print statements strategically
   - Leverage the Python debugger (pdb)
   - Write clear error messages

3. **Performance**
   - Use appropriate data structures
   - Avoid unnecessary loops and operations
   - Consider memory usage for large datasets

4. **Testing**
   - Write tests before or while writing code
   - Test edge cases and boundary conditions
   - Use assertions for debugging

5. **Documentation**
   - Write clear docstrings
   - Comment complex logic
   - Keep documentation up-to-date
