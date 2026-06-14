# calculator

import math

class Calculator:
    def __init__(self):
        self.total = 0.0

    def set_initial_number(self, number):
        self.total = float(number)

    def add(self, next_number):
        self.total += next_number
    def subtract(self, next_number):
        self.total -= next_number

    def multiply(self, next_number):
        self.total *= next_number

    def divide(self, next_number):
        if next_number == 0:
            print("Error: Cannot divide by zero.")
        else:
            self.total /= next_number

    def square_root(self):
        if self.total < 0:
            print("Error: Cannot take the square root of a negative number.")
        else:
            self.total = math.sqrt(self.total)

    def get_result(self):
        return int(self.total) if self.total.is_integer() else self.total



my_calc = Calculator()

first_num = input("Enter the first number: ")
my_calc.set_initial_number(first_num)

while True:
    process = input("Enter the process (+, -, *, /, root, end): ")
    
    if process == "end":
        print("Final result: ", my_calc.get_result())
        break
        
    if process == "root":
        my_calc.square_root()
        print("Current total: ", my_calc.get_result())
        continue
        
    next_number = float(input("Enter the next number: "))
    
    if process == "+":
        my_calc.add(next_number)
    elif process == "*":
        my_calc.multiply(next_number)
    elif process == "/":
        my_calc.divide(next_number)
    elif process == "-":
        my_calc.subtract(next_number)
    else:
        print("Error: Invalid process")
        continue

    print("Current total: ", my_calc.get_result())
