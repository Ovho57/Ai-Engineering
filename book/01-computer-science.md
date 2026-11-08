# 01 — Computer Science Foundations

## Computers and programs
A computer receives input, processes it using instructions, stores information, and produces output. A **program** is a set of instructions. Computers follow instructions; they do not automatically know our intentions.

**Algorithm:** a finite, ordered, clear set of steps for solving a problem. Example, maximum of A and B: receive both; compare; output the larger. **Pseudocode** describes logic without exact language syntax:

```text
INPUT A, B
IF A > B: OUTPUT A
ELSE: OUTPUT B
```

## Variables and types
A variable name refers to a value. Python examples:
```python
age = 15          # integer
rate = 0.01       # float
name = "AI"       # string
ready = True      # Boolean
```

An **expression** produces a value. Arithmetic: `+ - * / // % **`. Comparisons: `== != > < >= <=`. Remember `=` assigns; `==` compares.

## Conditions
```python
score = 70
if score >= 50:
    print("Pass")
else:
    print("Try again")
```
The condition is evaluated as true or false; one branch executes.

## Loops
```python
for i in range(5):
    print(i)  # 0,1,2,3,4
```
`range(5)` excludes 5. A `while` loop repeats as long as its condition is true:
```python
count = 0
while count < 3:
    print(count)
    count += 1
```
Ensure the condition changes when you intend the loop to end.

## Functions
Functions package reusable behavior:
```python
def square(x):
    return x * x

print(square(4))
```
Parameters receive input; `return` sends a result to the caller. Functions divide complex problems into manageable pieces.

## Data structures
Lists store ordered values: `scores = [80, 92, 75]`. Dictionaries store key-value pairs: `student = {"name": "Ama", "score": 92}`. AI uses collections, arrays, and tensors to represent data.

## Debugging
A bug is unintended behavior. Read the error, identify the line, reproduce with a small input, inspect values, and change one thing at a time. Debugging is a core engineering skill.

## Algorithm complexity
Complexity describes how work grows with input size n. O(1) is constant-like, O(n) grows linearly, and O(n²) often comes from nested loops. A method that works for 100 examples may be too slow for millions.

## Exercises
1. Pseudocode for the smallest of three numbers.
2. Print multiples of 3 from 3 to 30.
3. Function converting minutes to seconds.
4. Explain variable vs function vs algorithm.
5. Why can O(n²) be expensive for a million values?

## Mini-project
Create a number guessing game: choose a secret number, accept guesses, say too high/low, stop on correct guess, and count attempts.