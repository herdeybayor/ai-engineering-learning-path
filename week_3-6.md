# Python Fundamentals Guide - Weeks 3-6

## Introduction

Welcome to your Python fundamentals journey! Over the next four weeks, you'll learn the building blocks of Python programming. This guide is designed for complete beginners, taking you from basic concepts to writing your first meaningful programs. Remember: programming is like learning a new language - it takes practice and patience, but every small step counts.

## Week 3: Getting Started with Python Basics

### Day 1-2: Understanding Variables and Data Types

#### What are Variables?
Variables are like containers that store information. Think of them as labeled boxes where you can put different types of data.

```python
# Creating your first variables
name = "Alice"              # A string (text)
age = 25                    # An integer (whole number)
height = 1.75              # A float (decimal number)
is_student = True          # A boolean (True/False)

# Printing variables
print(name)                # Output: Alice
print(f"Age: {age}")      # Output: Age: 25
```

#### Practice Exercise:
Create variables to store information about yourself and print them using different formats.

### Day 3-4: Numbers and Basic Operations

```python
# Basic arithmetic operations
addition = 5 + 3           # 8
subtraction = 10 - 4       # 6
multiplication = 3 * 4     # 12
division = 15 / 3          # 5.0
integer_division = 15 // 2 # 7 (removes decimal)
remainder = 15 % 4         # 3 (modulo)
power = 2 ** 3            # 8 (2 to the power of 3)

# Working with different number types
price = 9.99              # float
quantity = 3              # integer
total = price * quantity
print(f"Total: ${total:.2f}")  # Format to 2 decimal places
```

### Day 5: Strings and Text Manipulation

```python
# String operations
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name  # Concatenation

# String methods
print(full_name.upper())          # JOHN DOE
print(full_name.lower())          # john doe
print(full_name.split())          # ['John', 'Doe']
print(len(full_name))            # 8 (length of string)

# String formatting
age = 30
message = f"Hello, my name is {full_name} and I am {age} years old"
```

## Week 4: Control Flow and Decision Making

### Day 1-2: Conditional Statements (if/else)

```python
# Basic if statement
age = 18
if age >= 18:
    print("You are an adult")
else:
    print("You are a minor")

# Multiple conditions
score = 85
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
else:
    grade = "F"

# Combining conditions
is_sunny = True
is_warm = True
if is_sunny and is_warm:
    print("Perfect day for a picnic!")
```

### Day 3-4: Loops

#### While Loops
```python
# Basic while loop
count = 0
while count < 5:
    print(count)
    count += 1

# With break and continue
number = 0
while True:
    number += 1
    if number == 3:
        continue  # Skip 3
    if number > 5:
        break    # Stop at 6
    print(number)
```

#### For Loops
```python
# Looping through ranges
for i in range(5):
    print(i)  # Prints 0 to 4

# Looping through strings
name = "Python"
for char in name:
    print(char)

# Looping through lists
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

### Day 5: Lists and Collections

```python
# Creating and modifying lists
numbers = [1, 2, 3, 4, 5]
numbers.append(6)         # Add to end
numbers.insert(0, 0)     # Add at position
numbers.remove(3)        # Remove value
popped = numbers.pop()   # Remove and return last item

# List operations
mixed = [1, "hello", 3.14, True]
print(len(mixed))        # Length of list
print(mixed[0])         # First item
print(mixed[-1])        # Last item
print(mixed[1:3])       # Slicing (items 1 to 2)
```

## Week 5: Functions and Modules

### Day 1-2: Creating Functions

```python
# Basic function
def greet(name):
    return f"Hello, {name}!"

# Function with multiple parameters
def calculate_total(price, quantity, tax_rate=0.1):
    subtotal = price * quantity
    tax = subtotal * tax_rate
    return subtotal + tax

# Using the functions
message = greet("Alice")
total = calculate_total(9.99, 2)  # Using default tax_rate
```

### Day 3-4: Advanced Function Concepts

```python
# Multiple return values
def get_user_info():
    name = "John"
    age = 30
    return name, age

# Functions with variable arguments
def sum_all(*numbers):
    total = 0
    for num in numbers:
        total += num
    return total

# Lambda functions (small, anonymous functions)
square = lambda x: x ** 2
```

### Day 5: Working with Modules

```python
# Importing modules
import random
import math
from datetime import datetime

# Using module functions
random_number = random.randint(1, 10)
square_root = math.sqrt(16)
current_time = datetime.now()
```

## Week 6: Error Handling and Basic File Operations

### Day 1-2: Understanding Errors and Exceptions

```python
# Basic try/except
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print(result)
except ValueError:
    print("Please enter a valid number")
except ZeroDivisionError:
    print("Cannot divide by zero")
finally:
    print("This always runs")
```

### Day 3-4: File Operations

```python
# Writing to a file
with open("example.txt", "w") as file:
    file.write("Hello, World!\n")
    file.write("This is a new line.")

# Reading from a file
with open("example.txt", "r") as file:
    content = file.read()
    print(content)

# Reading line by line
with open("example.txt", "r") as file:
    for line in file:
        print(line.strip())
```

### Day 5: Final Project - Command Line Calculator

```python
def calculator():
    """A simple command-line calculator."""
    while True:
        print("\nSimple Calculator")
        print("1. Add")
        print("2. Subtract")
        print("3. Multiply")
        print("4. Divide")
        print("5. Exit")
        
        try:
            choice = int(input("Enter choice (1-5): "))
            if choice == 5:
                print("Goodbye!")
                break
                
            num1 = float(input("Enter first number: "))
            num2 = float(input("Enter second number: "))
            
            if choice == 1:
                result = num1 + num2
            elif choice == 2:
                result = num1 - num2
            elif choice == 3:
                result = num1 * num2
            elif choice == 4:
                if num2 == 0:
                    print("Error: Cannot divide by zero!")
                    continue
                result = num1 / num2
            else:
                print("Invalid choice!")
                continue
                
            print(f"Result: {result}")
            
        except ValueError:
            print("Please enter valid numbers!")
        except Exception as e:
            print(f"An error occurred: {e}")

# Run the calculator
if __name__ == "__main__":
    calculator()
```

## Daily Practice Exercises

1. Create a program that calculates your age in days
2. Build a simple temperature converter (Celsius to Fahrenheit)
3. Make a program that generates a random password
4. Create a basic to-do list manager
5. Build a number guessing game

## Tips for Success

1. Code every day, even if just for 30 minutes
2. Type out all examples manually - don't copy and paste
3. Experiment by modifying the example code
4. Use print statements to understand how your code works
5. Keep a programming journal to track your learning
6. Don't be afraid to make mistakes - they're valuable learning opportunities

## Additional Resources

- Python's official documentation: docs.python.org
- Interactive Python practice: pythontutor.com
- Python exercises: practicepython.org
- Code challenges: codewars.com

Remember: The key to learning programming is practice and persistence. Don't worry if something doesn't make sense immediately - keep experimenting and asking questions. Happy coding!
