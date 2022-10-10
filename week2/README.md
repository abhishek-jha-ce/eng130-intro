# Week 2 - Python and GitHub

## Day #1 - Python Basics

Python is a high-level, general-purpose programming language. It is very popular because of its easy syntax and not complicated for begineers to learn. It supports multiple programming paradigms, including structured, object-oriented and functional programming. It is often described as a "batteries included" language due to its comprehensive standard library.

## Variables

In **Python**, Variables are containers for storing data values. Python has no command for declaring a variable. A variable is created the when we first assign a value to it. Today we learned 4 different data types of variables:

1. **Integer**: Whole numbers
2. **Float**: Decimal point numbers.
3. **String**: Series of characters surrounded by either single quotation marks, or double quotation marks.
4. **Boolean**: Represent one of two values: True or False.

Some examples of variables:

```
num = 5              # num is an integer
height = 14.2        # height is float
first_name = "John"  # first_name is a string
is_resident = True   # is_resident is a boolean value
```
**Note**: Variable names are case sensitive.

## Comments

Python comments start with the # character and extend to the end of the line. We can start a comment from the start of the line, after some whitespaces or code.

- If we want to toggle a comment for multiple line we can use: **CTRL + /**

## Checking data types of variable

The **type()** method returns class type of the argument(object) passed as parameter.

```
print(type(num))          # Expected Output: <class 'int'>
print(type(height))       # Expected Output: <class 'float'>
print(type(first_name))   # Expected Output: <class 'str'> 
print(type(is_resident))  # Expected Output: <class 'bool'> 
```

### Python First Exercise

```
first_name = input("Enter your first name: ")
last_name = input("Enter your last name: ")
print("Your name is " + first_name + " " + last_name)

dob = input("Enter you Date of Birth: ")
course_name = input("Enrolled Course Name: ")
resident = input("Are you a UK resident: ")
print(dob)
print(course_name)
print(resident)

Expected Output: 

Enter your first name: Abhishek
Enter your last name: Jha
Your name is Abhishek Jha
Enter you Date of Birth: 01/02/2002
Enrolled Course Name: DevOps
Are you a UK resident: Yes
01/02/2002
DevOps
Yes
```
