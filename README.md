# DSACrashCoursePractice
Python Concepts & Best Practices
Code Quality
Efficiency and readability are core best practices when writing Python
Aim for: consistency, readability, efficiency, performance
Follow PEP 8 standards (Python's official style guide)
Walrus Operator (:=)

Lets you assign a value to a variable as part of an expression, instead of on a separate line.

python
if (n := len(data)) > 10:
    print(f"List is too long ({n} elements)")
Scope of Variables — LEGB Rule

Python looks up variable names in this order:

Local — inside the current function
Enclosing — inside any enclosing function (closures)
Global — at the top level of the module
Built-in — Python's built-in names (e.g. len, print)
Object Identity vs. Object Equality
== checks if two objects have the equal values
is checks if two objects are the same object in memory (identity)
Variable assignment (b = a) makes b point to the same object as a
Shallow copy (c = a.copy()) creates a new object with copied top-level contents
Mutable vs. Immutable
Mutable (lists, dicts, sets): data can be changed in place, memory address stays the same
Immutable (strings, numbers, tuples): data cannot be changed — any "change" creates a new object at a new memory address
Tuples

Structured and can store multiple different data types in one object:

python
user = (25, "Alice", 5.9, True, {1, 2, 3}, [1, 2, 3], {"key": "value"})
Access elements with [], indexing starts at 0 (same as lists)
Unpack into variables:
python
a, b, c = my_tuple
Conditionals
python
if condition:
    ...
elif other_condition:
    ...
else:
    ...
Default "Falsy" Values

These are all treated as False in an if condition (everything else is True):

python
0, "", [], {}, None, False
Ternary Expression
python
status = "Adult" if age >= 18 else "Minor"
Chained Comparisons
python
if 0 < x < 10:
    print("x is between 0 and 10")
in / not in
python
if grade in ("A", "B"):
    print("Great job!")
match / case (structural pattern matching)
python
match status_code:
    case 200:
        print("OK")
    case 404 | 500:
        print("Error")
Short-Circuit Evaluation
python
name = user_input or default

If user_input is truthy, name gets user_input; otherwise it falls back to default.

Best Practice: Don't Compare Booleans Explicitly
python
# Good
if is_valid:
    ...

# Avoid
if is_valid == True:
    ...
