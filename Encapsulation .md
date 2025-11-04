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
