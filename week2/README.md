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
## Git & GitHub

**Git** is a free and open source software for distributed version control. It tracks changes in any set of files, and used in DevOps for coordinating work among the team. We can download git from [https://git-scm.com/](https://git-scm.com/downloads). When we download git, it downloads two additional components **Git Bash** and **Git GUI**.
- **Git Bash**: Git Bash is an application for Microsoft Windows environments which provides an emulation layer for a Git command line experience. It is similar to terminal for linux or powershell for windows.
- **Git GUI**: Git GUI is a graphical user interface for git that allows us to make changes to the repository by making new commits, amending existing ones, creating branches, performing local merges, and fetching/pushing to remote repositories.

**GitHub** is an online repository and hosting service for Software Development and Version Control using Git. It provides the distributed version control of Git plus access control, bug tracking, software feature requests, task management, continuous integration, and wikis for every project.

## Git Workflow

When we are done with our work or changes, in the Git VCS we have to follow the following steps:

- Check the status of our work, to identify if anything has been changed. `git status` command will show if there are any changes made.
- Add the changed files to the staging area.
``` 
git add <filename> [To add individual file to the staging area.]
git add . [To add all the file at once to the staging area.]
```
- Commit to the git folder. A message along with the commit is *highly recommended*.
```
git commit -m "Initial Commit"
```
- Once the commit is successfully done, we can push our code to the remote repository (GitHub in our case). We rename our branch to main to avoid any confusion.
```
git branch -M main
git push -u origin main
```
The -u flag creates a tracking reference for every branch that we successfully push onto the remote repository.

![Git Workflow](images/github-workflow.png)

## Connecting Git to GitHub via SSH

To connect our project stored on the local host(local machine) via SSH, first we need to create a public and private key. The private key is for our use, and the public key will be uploaded in our github settings so we can connect to it securely. These are the steps we must follow to connect them.

1. Navigate to the SSH folder in our local machine. If the directory doesn't exist we get the error as shown below. We have to create one.

<p align="center">
  <img src="https://user-images.githubusercontent.com/110366380/194913897-a9feedda-c4d6-40e8-9186-43f8b66c4640.png">
<![image](https://user-images.githubusercontent.com/110366380/194913897-a9feedda-c4d6-40e8-9186-43f8b66c4640.png)>
</p>

2. We can create the directory using `mkdir` command, and navigate to it using `cd` command. Ignore the `mkdir` command if the folder already exist.

<p align="center">
 <img src="https://user-images.githubusercontent.com/110366380/194914231-f6424269-a4c7-4885-961d-8c78ebbfac73.png">
<![image](https://user-images.githubusercontent.com/110366380/194914231-f6424269-a4c7-4885-961d-8c78ebbfac73.png)>
</p>

3. Once we are inside that folder, we can generate the SSH key by using the following commands:

```
$ssh-keygen -t rsa -b 4096 -C "youremail@domain.com"
```
**Note**: This command is for **Windows** Machine only.

4. It will ask us to enter the *filename* and *passphrase*, press enter and leave these field blank.

```
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/junus/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/junus/.ssh/id_rsa
Your public key has been saved in /c/Users/junus/.ssh/id_rsa.pub
The key fingerprint is:
SHA256:b+weJPVOFqec0cathTDMjivWy1BtP63B2bWj+cw4KMRnQ youremail@domain.com
The key's randomart image is:
+---[RSA 4096]----+
|         . ..o.  |
|        . o. +.  |
|       . o..* o  |
|        .o+EoB   |
|        S.o*B.   |
|         *=+o  . |
|        ..B+o.oo=|
|         = +o.oOo|
|        ..o  .o +|
+----[SHA256]-----+
```

5. If we see the response similar to above in our terminal, it means the key has been successfully generated. We can check them by using `ls` command. We should have 2 file(keys), a private key and a public key with the `.pub` extension.

 <p align="center">
 <img src="https://user-images.githubusercontent.com/110366380/194916150-e82e0d4d-32ab-4c8d-bf73-7905c2f330cf.png">
 <![image](https://user-images.githubusercontent.com/110366380/194916150-e82e0d4d-32ab-4c8d-bf73-7905c2f330cf.png)>
 </p>
 
6. We can now copy the public key to paste it into github. We access it using the `cat` command. The cat command is a utility command in Linux and is commonly used to print the content of a file onto the terminal. 

 <p align="center">
 <img src="https://user-images.githubusercontent.com/110366380/194916430-b0bf07a9-5a9f-4720-afc4-fd999aa07022.png">
 <![image](https://user-images.githubusercontent.com/110366380/194916430-b0bf07a9-5a9f-4720-afc4-fd999aa07022.png)>
 </p>
  
7. We now navigate to `settings`, in our github account by clicking our profile on the top right. Then from the left blade, we select `SSH and GPG keys` under `access` section.

![image](https://user-images.githubusercontent.com/110366380/194918204-b091f9c4-26b3-4a68-a5a7-3031c521015d.png)

8. Now we click on the new SSH key button and paste the earlier copied public key onto it. Make sure to give it a name, so that it can be easily identified later.

9. We have successfully connected our local machine (local git) to git hub using SSH.

## Connecting PyCharm integrated terminal to GitHub

1. Open PyCharm as administrator, to avoid any issues with account privileges in our local computer.
2. Open the terminal, and commit the changes to the file following the steps shown in Git Workflow Section.
3. Connect localhost, to remote github repository, using the following command:
    ```
    git remote add origin git@github.com:example_user/example_repo.git
    ```
4. **Blocker** It Should successfully connect or you might get an error saying `Author Identity Unknown`:

 <p align="center">
 <img src="https://user-images.githubusercontent.com/110366380/194922591-0881d726-d65a-432b-bf28-208fc41057c2.png">
 <![image](https://user-images.githubusercontent.com/110366380/194922591-0881d726-d65a-432b-bf28-208fc41057c2.png)>
 </p>
 
5. **Blocker** We can update our username and user email as required, following the commands:
    ```
    git config --global user.name "FIRST_NAME LAST_NAME"
    git config --global user.email "you@example.com"
    ```
6. **Blocker** Another possible error we might encounter if we don't copy and paste the public key correctly. Watch out for white spaces.

 <p align="center">
 <img src="https://user-images.githubusercontent.com/110366380/194923346-2fc0a1fa-72e6-4520-9a4e-a502dfc4f824.png">
 <![image](https://user-images.githubusercontent.com/110366380/194923346-2fc0a1fa-72e6-4520-9a4e-a502dfc4f824.png)>
 </p>

7. If these blockers are corrected or does not occur we can successfully push our commited files to our repository using the connection through SSH.
 <p align="center">
 <img src="https://user-images.githubusercontent.com/110366380/194923830-4f698bc9-c916-4f96-910f-1ac7270d96ff.png">
 <![image](https://user-images.githubusercontent.com/110366380/194923830-4f698bc9-c916-4f96-910f-1ac7270d96ff.png)>
 </p>

## Day #2 - Python & Git Contd..

### Git Help
```
usage: git [-v | --version] [-h | --help] [-C <path>] [-c <name>=<value>]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           [--super-prefix=<path>] [--config-env=<name>=<envvar>]
           <command> [<args>]

These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone     Clone a repository into a new directory
   init      Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add       Add file contents to the index
   mv        Move or rename a file, a directory, or a symlink
   restore   Restore working tree files
   rm        Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect    Use binary search to find the commit that introduced a bug
   diff      Show changes between commits, commit and working tree, etc
   grep      Print lines matching a pattern
   log       Show commit logs
   show      Show various types of objects
   status    Show the working tree status

grow, mark and tweak your common history
   branch    List, create, or delete branches
   commit    Record changes to the repository
   merge     Join two or more development histories together
   rebase    Reapply commits on top of another base tip
   reset     Reset current HEAD to the specified state
   switch    Switch branches
   tag       Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch     Download objects and refs from another repository
   pull      Fetch from and integrate with another repository or a local branch
   push      Update remote refs along with associated objects
```
## Python

### Intro to Data types & Operators
### - `+` `-` `*` `/`

### Comparison Operators
- `>` greater than
- `<` less than
- `==` True or False
- `>=` greater than or equal
- `<=` less than or equal

```
a = 24
b = 16

print(a+b) # outcome added value of a & b
print(a-b) # outcome substraction value of a & b

# Comparison
print(a>b) # True
print(a<b) # False
```

#### Modulo Operator `%`

The `%` symbol in Python is called the Modulo Operator. It returns the remainder of dividing the left hand operand by right hand operand.

#### Use Case:


#### Not Equal Operator `!=`


```commandline
# Built in Methods
# DRY - Don't Repeat Yourself
# - print()
greeting = "Hello World!"
print(greeting)
print(greeting.isalpha())        # Check if the variable is alphabet Only
print(greeting.islower())        # Check if the variable is in lowercase
print(greeting.startswith('H'))  # Check if starts with a specified letter
print(greeting.endswith('!'))    # Check if ends with a specified letter

```

```commandline
# String
# String indexing - starts from 0
# H e l l o   W o r l d  !
# 0 1 2 3 4 5 6 7 8 9 10 11
#           -2-1

greeting = "Hello World!"
print(greeting)
# len method checks the length of the string
print(len(greeting))

# Forward Indexing
print(greeting[0:5])   # Prints Hello
print(greeting[6:12])  # Prints World!

# Reverse Indexing
print(greeting[-12:-6]) # Prints Hello
print(greeting[-6:])   # Prints World!
```

```commandline
# Available String Method
white_space = "lot's of spaces at the end                                "
print(len(white_space))
# strip() removes white space
print(len(white_space.strip())) # this will remove all the white at the end.
Example_text = "abhishek here's sOme text wIth lOt's of text"
# Count no. of occurrence
print(Example_text.count("text"))
# lower case and upper case and Capitalize
print(Example_text)
print(Example_text.lower())
print(Example_text.upper())
print(Example_text.capitalize())
# replace
print(Example_text.replace("wIth", ","))
```


### Concatenation & Casting
- adding strings together
 - casting/converting data types
```commandline
# User data input
first_name = "abhishek"
last_name = "jha"
salary = 40

print(first_name)
print(last_name)
print(first_name.capitalize() + " " + last_name.capitalize())  # Concatenation
print(first_name + " " + last_name + " earns a salary of £" + str(salary))  # Casting int to string before concatenating
print(f"{first_name} {last_name} earns a salary of £{salary}")  # Another way of writing it

Expected Output:
abhishek
jha
Abhishek Jha
abhishek jha earns a salary of £40
abhishek jha earns a salary of £40
```

### Exercise 2.1

```commandline
Using what we have learned so far let's head back to our user_details_capture file and ensure we are using / casting the same type. Extend the capture further to grab details such as address (ensuring that a house number is correctly represented, hobbies, etc. and respond to the user the details they have provided.

first_name = input("Enter your first name: ")
last_name = input("Enter your last name: ")
address = input("Enter your address: ")
dob = input("Enter you Date of Birth: ")
course_name = input("Enrolled Course Name: ")
is_resident = input("Are you a UK resident: ")

address_list = address.split(" ")
house_no = address_list[0]
# street_address = address_list[1 : -2]
post_code = address_list[-2] + " " + address_list[-1]

#house_no = address.split(" ")[0];
#post_code = address.split(" ")[-2] + " " + address.split(" ")[-1]
print(f"Hello {first_name} {last_name}.")
print(f"Your House Number is: {house_no}")
# print(f"Your Street Address is: {street_address}")
print(f"Your post code is {post_code}")
print("Your Date of Birth is: " + dob) # Another way of printing
print("You Are Enrolled in " + course_name + " and you have to be a " + is_resident)
```

### Data Collections

#### Lists

```commandline
# syntax list_name = ["one", "two", "three"]

#Apply DRY
shopping_list = ["ketchup", "fanta", "eggs", "bread"]
print(shopping_list)
print(type(shopping_list))
shopping_list.append('chicken')
print(shopping_list)  # add an item to the list
print(shopping_list[2])
shopping_list[2] = "Icecream"  # replacing an item with another one in the list
print(shopping_list)
shopping_list.remove('fanta')  # removing an item from the list using value
shopping_list.pop(1)  # removing an item from the list using index
print(shopping_list)

# Can list have multiple types
multiple_type = [1, 2, 3, "One", "two", 4, "three"]
print(multiple_type)
print(multiple_type[2])

Output:
[1, 2, 3, 'One', 'two', 4, 'three']
3
```

#### Tuples

```commandline
# Tuples
# Immutable - can't be changed - edited - added
# For e.g. In user_details Date Of Birth never change
# Syntax ("")
essentials = ("milk", "paracetamol", "drinks")
print(essentials)
print(type(essentials))

essentials[0] = "coffee"  # result in error as it's immutable
print(essentials)

Output
('milk', 'paracetamol', 'drinks')
<class 'tuple'>
Traceback (most recent call last):
  File "C:\Users\abhis_h1xa3es\Python\eng130_python\data_collections.py", line 35, in <module>
    essentials[0] = "coffee"
TypeError: 'tuple' object does not support item assignment
```

### W3School Challenge Exercise
- Challenge Exercise Completed till Tuples

![image](https://user-images.githubusercontent.com/110366380/195140523-f78d9987-cac6-411c-bfa9-b4f0f4988bc8.png)


#### Dict

- What is a Dictionary - Data Collection Type
- How to manage Dictionaries - How to manage the data using Dict
- It works as key value pair key = value
- syntax { "name" : "Sparta" }

```
# store student's data - name, course_name, progress, completed_lessons
student_1 = {
    "key": "values",
    "name": "Abhishek",
    "stream": "DevOps",
    "completed_lessons": 4,
    "completed_lessons_names": ["lists", "tuples", "strings"]
}

print(type(student_1))  # Prints <class 'dict'>
print(student_1["stream"])  # Prints DevOps
print(student_1["completed_lessons_names"])  # Prints ['lists', 'tuples', 'strings']
print(student_1["completed_lessons_names"][0])  # Prints lists
print(student_1["completed_lessons_names"][1])  # Prints tuples
print(student_1["completed_lessons_names"][2])  # Prints strings

```
