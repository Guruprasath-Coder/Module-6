# # Constructors in Python: Welcome Message with Student Name

## 🎯 Aim
To write a Python program that creates a **Student** class with a **default constructor** and a method to display a welcome message along with the student’s name provided by the user.

## 🧠 Algorithm
1. **Get user input**: Accept the student's name from the user.
2. **Define the class**: Create a class `Student` with a default constructor (`__init__`).
3. **Default Constructor**: In the constructor, assign the user input (student name) to an instance variable `self.a`.
4. **Display Message**: Define a method `show` that prints "This is non-parameterized constructor" and a welcome message with the student’s name.
5. **Execute the Program**: Instantiate the `Student` class and call the `show` method.

## 🧾 Program
```python
class Student:
    def __init__(self):
        self.a = input("Enter Student Name: ")

    def show(self):
        print("This is non-parameterized constructor")
        print("Welcome,", self.a)
s1 = Student()
s1.show()
```
## Output
<img width="838" height="220" alt="image" src="https://github.com/user-attachments/assets/45adc714-ae27-4e3a-bb64-85338bbb11c5" />


## Result
The program successfully demonstrates the use of a default constructor in Python by taking a student’s name as input and displaying a welcome message along with the constructor message.

# Destructor in Python

This project demonstrates how to implement a **destructor** in Python using a simple class.

## 🚀 Overview

The program defines a class `Demo` with:

- A **constructor** `__init__` that initializes an instance variable and prints a message.
- A **destructor** `__del__` that prints a message when the object is destroyed.

## 🧠 Algorithm

1. Define a class named `Demo`.
2. Inside the class, define the `__init__` method:
   - Initialize an instance variable `status` with the value `"Alive"`.
   - Print the value of `status`.
3. Define the `__del__` method:
   - Print a message indicating the object is being destroyed.
4. Outside the class:
   - Create an instance of the `Demo` class.
   - Delete the object using the `del` keyword.
## Program
```python
class Demo:
    def __init__(self):
        self.status = "Alive"
        print("Constructor called, status:", self.status)

    def __del__(self):
        print("Destructor called, object destroyed")
obj = Demo()
del obj
```

## 🧪 Output
<img width="595" height="163" alt="image" src="https://github.com/user-attachments/assets/45257350-6528-45f1-bd76-344cd37d6330" />

## Result
Thus, the program successfully demonstrates the use of constructor and destructor in Python.

# Hierarchical Inheritance in Python

This Python project demonstrates **Hierarchical Inheritance** using a base class `Details` and two derived classes `Employee` and `Patient`. The program collects and displays details for both employees and patients.

## 🎯 Aim

To write a Python program that uses **Hierarchical Inheritance** to input and display **Employee** and **Patient** details.

## 📘 Description

- **Base Class:** `Details`
  - Stores common attributes: `name`, `age`
  - Provides methods: `getName()`, `getAge()`

- **Derived Class 1:** `Employee`
  - Inherits from `Details`
  - Adds: `employee_id`, `department`
  - Method: `getEmployeeDetails()`

- **Derived Class 2:** `Patient`
  - Inherits from `Details`
  - Adds: `patient_id`, `disease`
  - Method: `getPatientDetails()`

## 🧠 Algorithm

1. Create base class `Details` with common attributes.
2. Create `Employee` class extending `Details`, adding employee-specific data.
3. Create `Patient` class extending `Details`, adding patient-specific data.
4. Get user input for employee and patient data.
5. Display collected information using class methods.

## Program
```python

class Details:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def getName(self):
        return self.name
    
    def getAge(self):
        return self.age


class Employee(Details):
    def __init__(self, name, age, employee_id, department):
        super().__init__(name, age)
        self.employee_id = employee_id
        self.department = department
    
    def getEmployeeDetails(self):
        print("\n--- Employee Details ---")
        print(f"Name       : {self.getName()}")
        print(f"Age        : {self.getAge()}")
        print(f"Employee ID: {self.employee_id}")
        print(f"Department : {self.department}")


class Patient(Details):
    def __init__(self, name, age, patient_id, disease):
        super().__init__(name, age)
        self.patient_id = patient_id
        self.disease = disease
    
    def getPatientDetails(self):
        print("\n--- Patient Details ---")
        print(f"Name      : {self.getName()}")
        print(f"Age       : {self.getAge()}")
        print(f"Patient ID: {self.patient_id}")
        print(f"Disease   : {self.disease}")



if __name__ == "__main__":
    
    emp_name = input("Enter Employee Name: ")
    emp_age = int(input("Enter Employee Age: "))
    emp_id = input("Enter Employee ID: ")
    emp_dept = input("Enter Department: ")
    emp = Employee(emp_name, emp_age, emp_id, emp_dept)
    
    
    pat_name = input("\nEnter Patient Name: ")
    pat_age = int(input("Enter Patient Age: "))
    pat_id = input("Enter Patient ID: ")
    pat_disease = input("Enter Disease: ")
    pat = Patient(pat_name, pat_age, pat_id, pat_disease)
    
    
    emp.getEmployeeDetails()
    pat.getPatientDetails()

```
## Sample Output
<img width="811" height="229" alt="image" src="https://github.com/user-attachments/assets/c7ce9114-9cc3-4586-a672-1f749b467d4d" />

## Result
Thus, the Python program for Hierarchical Inheritance was successfully executed.
The base class Details was inherited by Employee and Patient classes, and details for both were collected and displayed correctly.


# Multilevel Inheritance Example in Python

This Python project demonstrates the concept of **Multilevel Inheritance** to collect and display the **name**, **age**, and **location** of a person.

## 🎯 Aim

To write a Python program that uses multilevel inheritance to get and display a person’s name, age, and location.

## 🧠 Algorithm

1. **Parent Class**  
   - `__init__(name)` initializes the `name` attribute.  
   - `getName()` returns the `name`.

2. **Child Class (inherits Parent)**  
   - `__init__(name, age)` initializes `name` using `super()` and adds `age`.  
   - `getAge()` returns the `age`.

3. **Grandchild Class (inherits Child)**  
   - `__init__(name, age, location)` initializes `name` and `age` using `super()` and adds `location`.  
   - `getLocation()` returns the `location`.

4. **Input & Output**  
   - Take user input for name, age, and location.  
   - Create an instance of `Grandchild`.  
   - Print all details using class methods.

## Program
```python
class Person:
    def __init__(self, name):
        self.name = name

    def getName(self):
        return self.name


class Age(Person):
    def __init__(self, name, age):
        super().__init__(name)
        self.age = age

    def getAge(self):
        return self.age


class Location(Age):
    def __init__(self, name, age, location):
        super().__init__(name, age)
        self.location = location

    def getLocation(self):
        return self.location


name = input("Enter Name: ")
age = int(input("Enter Age: "))
location = input("Enter Location: ")


person1 = Location(name, age, location)



print("Name:", person1.getName())
print("Age:", person1.getAge())
print("Location:", person1.getLocation())

```
## Sample Output
<img width="584" height="181" alt="image" src="https://github.com/user-attachments/assets/f59e1195-c99d-4bed-82b6-f0c472869288" />

## Result
The program successfully demonstrates Multilevel Inheritance in Python by collecting and displaying a person’s name, age, and location using three classes.


# Arithmetic Operations Using Multiple Inheritance in Python

This Python program demonstrates **multiple inheritance** by performing basic arithmetic operations — Addition, Subtraction, and Division — using three classes.

## 🎯 Aim

To write a Python program to calculate **Add, Sub & Division** using **Multiple Inheritance**.

## 🧠 Algorithm

1. **Define `Calculation1` class**
   - Contains `Summation(a, b)` method to return the sum of two numbers.
2. **Define `Calculation2` class**
   - Contains `Subtraction(a, b)` method to return the difference of two numbers.
3. **Define `Derived` class**
   - Inherits from both `Calculation1` and `Calculation2`.
   - Contains `Division(a, b)` method to return the division result.
4. **Input**
   - Prompt the user to enter two numbers.
5. **Process**
   - Create an object of the `Derived` class.
   - Call `Summation`, `Subtraction`, and `Division` methods.
6. **Output**
   - Display the results of the three operations.

## 💻 Program 
```python
class Calculation1:
    def Summation(self, a, b):
        return a + b

class Calculation2:
    def Subtraction(self, a, b):
        return a - b

class Derived(Calculation1, Calculation2):
    def Division(self, a, b):
        if b == 0:
            return "Division by zero is not allowed"
        return a / b


a = int(input("Enter first number: "))
b = int(input("Enter second number: "))


obj = Derived()


print("Addition:", obj.Summation(a, b))
print("Subtraction:", obj.Subtraction(a, b))
print("Division:", obj.Division(a, b))
```
## Output Example
<img width="334" height="209" alt="image" src="https://github.com/user-attachments/assets/33a0230d-71ef-43a9-83db-de167871c1bf" />


## Result
This program successfully demonstrates multiple inheritance in Python by performing Addition, Subtraction, and Division using three classes.

https://github.com/Guruprasath-Coder/Module-5.git 🐍 Python OOP: Abstract Class & Method Example

## 🎯 AIM

To create an **abstract class** named `Shape` with an **abstract method** `calculate_area`, and implement this method in two subclasses: `Rectangle` and `Circle`.

---

## 🧠 ALGORITHM

1. **Import ABC module**:
   - Use `from abc import ABC, abstractmethod` to define abstract classes and methods.

2. **Create Abstract Class `Shape`**:
   - Define an abstract method `calculate_area()` with `@abstractmethod`.

3. **Create Subclass `Rectangle`**:
   - Set default values for `length` and `breadth`.
   - Override `calculate_area()` to compute the rectangle area.

4. **Create Subclass `Circle`**:
   - Set default value for `radius`.
   - Override `calculate_area()` to compute the circle area.

5. **Create Objects & Call Methods**:
   - Instantiate `Rectangle` and `Circle`.
   - Call their `calculate_area()` methods.

---

## 💻 Program
```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def calculate_area(self):
        pass

class Rectangle(Shape):
    def __init__(self, length, breadth):
        self.length = length
        self.breadth = breadth

    def calculate_area(self):
        return self.length * self.breadth

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def calculate_area(self):
        return 3.14 * self.radius * self.radius

rect = Rectangle(10, 5)
circle = Circle(7)

print("Area of Rectangle:", rect.calculate_area())
print("Area of Circle:", circle.calculate_area())

```
## Output
![image](https://github.com/user-attachments/assets/7b2ffd74-5cf9-4020-828a-e8a8f8a0cfc9)

## Result
The program successfully demonstrates the concept of abstract classes and methods in Python by implementing calculate_area() in both Rectangle and Circle subclasses.

# 🐍 Python OOP: Encapsulation with Private Members

## 🎯 AIM

To implement **Encapsulation** in Python by defining a class `Rectangle` with **private member variables** `__length` and `__breadth`.

---

## 🧠 ALGORITHM

1. **Define the Class**:
   - Create a class `Rectangle` with two private attributes: `__length` and `__breadth`.

2. **Initialize Variables**:
   - Use the `__init__()` constructor to set initial values for `__length` and `__breadth`.

3. **Print Values**:
   - Display the private variables from within the class to demonstrate access.

4. **Instantiate the Object**:
   - Create an object of the `Rectangle` class to trigger the constructor.

---

## 💻 Program
```python
class Rectangle:
    def __init__(self, length, breadth):
        self.__length = length      # private member
        self.__breadth = breadth    # private member
        print("Length:", self.__length)
        print("Breadth:", self.__breadth)
rect = Rectangle(10, 5)

```
## Output
![image](https://github.com/user-attachments/assets/63fc5989-f95c-4771-8490-bdff81b7eeb4)

## Result
The program successfully demonstrates Encapsulation in Python by using private members __length and __breadth in the Rectangle class.

# 🐟 Method Overriding-Fish and Shark Class Inheritance in Python

## 🧠 AIM:
To write a Python program that demonstrates class inheritance by creating a parent class `Fish` with a method `type`, and a child class `Shark` that overrides the `type` method.

## 📋 ALGORITHM:

1. Define the `Fish` class with a method named `type()` that prints `"fish"`.
2. Define the `Shark` class as a subclass of `Fish`, and override the `type()` method to print `"shark"`.
3. Create an instance of the `Fish` class named `obj_goldfish`.
4. Create an instance of the `Shark` class named `obj_hammerhead`.
5. Use a `for` loop to iterate over both objects.
6. Within the loop, call the `type()` method using the loop variable.
7. Output will demonstrate method overriding: printing `"fish"` and `"shark"` accordingly.

## 💻 PROGRAM:
```python
class Fish:
    def type(self):
        print("fish")

class Shark(Fish):
    def type(self):
        print("shark")

obj_goldfish = Fish()
obj_hammerhead = Shark()

for obj in (obj_goldfish, obj_hammerhead):
    obj.type()

```
## OUTPUT
![image](https://github.com/user-attachments/assets/fc84bcbd-4502-44b2-bd78-396bdd996d19)


## RESULT
The program successfully demonstrates method overriding in Python by creating a parent class Fish and a child class Shark that overrides the type() method.

# 🐍 Python OOP: Operator Overloading (Less Than `<`)

## 🎯 AIM

To write a Python program that demonstrates **operator overloading** by overloading the **less than (`<`)** operator using a custom class.

---

## 🧠 ALGORITHM

1. **Create Class `A`**:
   - Define the `__init__()` method to initialize the object with a value `a`.

2. **Overload the `<` Operator**:
   - Define the `__lt__()` method with logic:
     - If `self.a < o.a`, return `"ob1 is less than ob2"`
     - Else, return `"ob2 is less than ob1"`

3. **Create Objects**:
   - Instantiate two objects `ob1` and `ob2` with values.

4. **Use `<` Operator**:
   - Use `print(ob1 < ob2)` to trigger the overloaded behavior.

---

## 💻 Program
```python
class A:
    def __init__(self, a):
        self.a = a

    def __lt__(self, o):
        if self.a < o.a:
            return "ob1 is less than ob2"
        else:
            return "ob2 is less than ob1"

ob1 = A(5)
ob2 = A(10)

print(ob1 < ob2)
```

## Output
![image](https://github.com/user-attachments/assets/761afa5a-c67e-4397-a9d7-c3779c3fa61a)

## Result
The program successfully demonstrates operator overloading in Python by overriding the less than (<) operator using the __lt__() method.

# # 🐍 Python OOP: Polymorphism with Classes

## 🎯 AIM

To create two specific classes — `Beans` and `Mango`. Then, create a **generic function** that can accept any object and determine its **type** (Fruit or Vegetable) and **color**, using polymorphism.

---

## 🧠 ALGORITHM

1. **Create Class `Beans`**:
   - Define `type()` method that prints `"Vegetable"`.
   - Define `color()` method that prints `"Green"`.

2. **Create Class `Mango`**:
   - Define `type()` method that prints `"Fruit"`.
   - Define `color()` method that prints `"Yellow"`.

3. **Define Generic Function `func(obj)`**:
   - Call `obj.type()` and `obj.color()` — this works with both `Beans` and `Mango` objects, showcasing **polymorphism**.

4. **Create Objects**:
   - Instantiate `Beans` and `Mango`.
   - Pass them to `func()` and execute the program.

---

## 💻 Program
```python
class Beans:
    def type(self):
        print("Vegetable")
    def color(self):
        print("Green")

class Mango:
    def type(self):
        print("Fruit")
    def color(self):
        print("Yellow")

def func(obj):
    obj.type()
    obj.color()

obj1 = Beans()
obj2 = Mango()

func(obj1)
func(obj2)

```
## Output
![image](https://github.com/user-attachments/assets/2a50a3e8-3cee-455c-9ade-f6ed33b9411f)

## Result
The program successfully demonstrates polymorphism in Python OOP by using a generic function that works with different classes (Beans and Mango) and calls their respective methods.
