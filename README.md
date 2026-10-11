# 🐍Python Fundamentals: Loops, Control Statements & Functions

![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Anaconda](https://img.shields.io/badge/Topic-Loops,Functions-44A833?style=for-the-badge&logo=anaconda&logoColor=white)

---

## Overview

This project contains three small Python programs built as part of the **Python Fundamentals** course. Together they cover the core building blocks used in everyday data work: repeating tasks with loops, controlling program flow, and packaging logic into reusable functions.

| # | Program | Core concepts | Script |
|---|---------|---------------|--------|
| 1 | Number Guessing Game | `while` loop, `break`, `continue`, loop `else` | [`guessing_game.py`](guessing_game.py) |
| 2 | Multiplication Table Generator | `for` loop, `range()`, f-strings | [`multiplication_table.py`](multiplication_table.py) |
| 3 | BMI Calculator | Functions, `return`, type conversion | [`bmi_calculator.py`](bmi_calculator.py) |

## Objectives

- Use a `while` loop together with `break`, `continue` and `else` to control program flow.
- Iterate over a fixed range with a `for` loop.
- Write and call a function that takes inputs and returns a result.
- Read user input and convert it to the right data type (`int`, `float`).

## Tools

- Python 3.12
- Jupyter Notebook (Anaconda distribution)
- `random` module from the standard library

---

## Project Walkthrough

### 1. Number Guessing Game

**Problem.** The computer picks a random number from 1 to 10. The user has 3 attempts to guess it.

**Logic**

| Situation | What the program does |
|-----------|----------------------|
| Guess outside 1 to 10 | Shows a message and uses `continue`. The attempt is not counted. |
| Guess too high or too low | Shows a hint and reduces the attempts by one. |
| Correct guess | Shows a congratulation message and uses `break` to end the game. |
| Attempts run out | The loop's `else` block runs and shows "Better luck next time!". |

**Key code**

```python
while attempts > 0:
    guess = int(input("Guess the number (between 1 and 10): "))

    if guess < 1 or guess > 10:
        print("Your guess is out of range. Please guess a number between 1 and 10.")
        continue

    if guess == secret_number:
        print("Congratulations! You guessed the correct number.")
        break
    elif guess > secret_number:
        print("Too high. Try again.")
    else:
        print("Too low. Try again.")

    attempts -= 1
else:
    print(f"Better luck next time! The number was {secret_number}.")
```
---

### 2. Multiplication Table Generator

**Problem.** Print the multiplication table (1 to 10) for any number entered by the user.

**Logic.** A `for` loop runs over `range(1, 11)`. Each pass multiplies the user's number by the loop counter and prints the line in the format `number x i = result`.

**Key code**

```python
number = int(input("Enter the number for which you want the multiplication table: "))

for i in range(1, 11):
    result = number * i
    print(f"{number} x {i} = {result}")
```
---

### 3. BMI Calculator

**Problem.** Calculate the Body Mass Index from weight and height.

**Formula**

```
BMI = weight (kg) / height (m)²
```

**Logic.** The function `calculate_bmi(weight, height)` returns the BMI. The main program reads the weight and height as `float` values, calls the function, and prints the result rounded to two decimal places.

**Key code**

```python
def calculate_bmi(weight, height):
    return weight / (height ** 2)

weight = float(input("Enter your weight in kg: "))
height = float(input("Enter your height in meters: "))

bmi = calculate_bmi(weight, height)
print(f"Your BMI is: {bmi:.2f}")
```

> Height must be entered in **meters** (for example, 1.62), not feet or centimeters.
> 
## Repository Structure

```
python-assignment-3/
├── README.md
├── guessing_game.py
├── multiplication_table.py
├── bmi_calculator.py
├── notebook/
│   └── While_loop__For_loop_and_Function.ipynb
└── images/
    ├── guessing_game_output.png
    ├── multiplication_table_output.png
    ├── bmi_calculator_output.png
    └── code_and_output_overview.png
```

## Key Takeaways

- `continue` skips the rest of one loop pass, while `break` exits the loop completely.
- A loop's `else` block runs only when the loop finishes without hitting `break`.
- `input()` always returns text, so values must be converted with `int()` or `float()` before doing maths.
- Wrapping logic in a function makes it reusable and easy to test.

## Author

**Yallappagari Srihari**

**Aspiring Data Analyst**

**Python | SQL | Excel | Power BI**
