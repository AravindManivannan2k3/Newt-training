Section 1: First Steps – Variables & User Input

This section introduces basic Python concepts like variables and taking input from users. You learn how data is stored and used in programs.


name = input("Enter your name: ")
age = int(input("Enter your age: "))

print("Hello", name)
print("You are", age, "years old")
Section 2: Make Your App Interactive (Methods, While Loops)

Focuses on loops and string methods to make programs interactive and continuous.


while True:
    text = input("Type something (or 'exit'): ")
    
    if text == "exit":
        break
    
    print(text.upper())
Section 3: Control Program Flow (Match-Case, For Loops)

Introduces decision-making and structured control flow using loops and match-case.

 .:

command = input("Enter command: ")

match command:
    case "start":
        print("Starting...")
    case "stop":
        print("Stopping...")
    case _:
        print("Invalid command")
Section 4: Manipulate Data (Lists, Tuples)

Covers storing multiple values and accessing/modifying them.



fruits = ["apple", "banana", "cherry"]

fruits.append("mango")
print(fruits[1])  # banana
Section 5: Display & Structure Output (f-strings, enumerate)

Teaches clean and formatted output.

Example:

items = ["pen", "pencil", "eraser"]

for index, item in enumerate(items, start=1):
    print(f"{index}. {item}")
Section 6: Persist Data with Files

Focuses on reading and writing files.


with open("data.txt", "w") as file:
    file.write("Hello World")

with open("data.txt", "r") as file:
    print(file.read())
Section 7: Optimize Code (List Comprehensions)

Introduces concise and efficient coding techniques.



numbers = [1, 2, 3, 4]
squares = [n*n for n in numbers]

print(squares)
Section 8: File Management (Context Managers)

Explains safe file handling using with.



with open("notes.txt", "a") as file:
    file.write("New line added\n")
Section 9: Decision Making (If/Elif/Else, Dictionaries)

Covers logic building and structured decision making.


marks = 85

if marks > 90:
    print("A")
elif marks > 75:
    print("B")
else:
    print("C")
Section 10: Error Handling (Try-Except)

Prevents crashes using exception handling.


try:
    num = int(input("Enter number: "))
    print(10 / num)
except:
    print("Invalid input")
Section 11: Functions

Introduces reusable code blocks.


def greet(name):
    return f"Hello {name}"

print(greet("Aravind"))
Section 12: Function Arguments & Defaults

Covers advanced function usage.

def power(base, exp=2):
    return base ** exp

print(power(3))      # 9
print(power(2, 3))   # 8
Section 15: Built-in Tools & Version Control

Introduces modules and Git basics.


import math

print(math.sqrt(16))
Section 16: External Libraries

Teaches using third-party packages.



import requests

response = requests.get("https://api.github.com")
print(response.status_code)
Section 17–19: Task Manager App (Projects)

Builds real-world apps step-by-step (CLI → GUI → Web).

Example (basic CLI idea):

tasks = []

while True:
    task = input("Add task: ")
    tasks.append(task)
    
    print("Tasks:", tasks)
