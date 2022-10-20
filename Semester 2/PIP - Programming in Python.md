<label>Lecture 01 - 2022/10/04</label>
# Introduction to Programming
What is a computer program?
	- A set of instructions stored inside the computer memory that is carefully structured to perform a certain task.
	- A program is written in a programming language by a programmer.
		*Ex: Python, JavaScript, HTML, CSS, Java, C*

High level programming languages vs low level languages?
	High level programming languages are closer to modern day human languages with friendlier syntax, they implement higher computing concepts like,
		- Object orientation
		- Functional programming
		- Garbage collection

Compiler, Interpreter vs Assembler?
	- An Interpreter will execute source code inside a runtime line by line.
	- A compiler will translate source code into machine code/executable, checking all code at once. The executable can be executed later.
	- An assembler will translate low level code to machine code.
	- Compiled programs have faster execution speeds while using minimal resources without relying on a runtime.
	- Interpreted programs are comparatively slower as it is executed inside a runtime.
	- Interpreted languages are much more flexible compared to compiled languages as errors raised inside the runtime will not interrupt the program execution directly.
		*However the scope of the error raised and its dependents may interrupt the program execution at times. This is up to the programmers design.*
	- Interpreted languages need minimal code to be written as the runtime takes care of most of the boilerplate code that will take care of garbage collection, type checking etc.
	
Algorithm? Step by step procedure for solving a problem.
	What are the two ways of writing an algorithm,
		1. Flow chart
		2. Pseudocode

## Activity 01
1. Write a pseudo code that inputs two numbers (a and b) and calculates the sum of the numbers and output the sum.

```
BEGIN
	X = 0
	WHILE True:
		I = INPUT "Enter a number."
		
		IF I == "":
			BREAK
		ENDF
		
		TRY:
			X = X + INT(I)
		EXCEPT ValueError:
			OUTPUT "Invalid number."
			BREAK
	ENDWHILE
		
	OUTPUT "The total is : " + X
END
```

2. Write a pseudo code that inputs two numbers (a and b) and output the largest number.

```
BEGIN 
	INPUT A, B, "Enter the two numbers."
	
	IF A > B:
		OUTPUT "Number A({A}) is greater than number B({B})}."
	ElSE IF B > A:
		OUTPUT "Number B({B}) is greater than number A({A})}."
	ELSE:
		OUTPUT "Both numbers are equal."
	ENDIF
END
```

```python
from __future__ import annotations

from typing import TYPE_CHECKING

if TYPE_CHECKING:
    from typing import Any, Callable


def get_input(
    prompt: str,
    data_type: str = None,
    *,
    check: Callable[[Any], bool] = None,
    invalid_prompt: str = "Invalid input!",
    check_failure_prompt: str = "Check failure!",
) -> Any:
    prompt += "" if prompt.endswith(" ") else " "

    while True:
        data = input(prompt)
        
        if data_type:
	        try:
	            data = data_type(data)
	        except ValueError:
	            print(invalid_prompt)
	            continue

        if check:
            try:
                if check(data):
                    return data
                else:
                    raise ValueError
            except (ValueError, TypeError):
                print(check_failure_prompt)
                continue
        else:
            return data


if __name__ == "__main__":
    A = get_input("Input number A:", int, invalid_prompt="Not a number!")
    B = get_input("Input number B:", int, invalid_prompt="Not a number!")
    
    if A > B:
        print("A is more than B.")
    elif B < A:
        print("B is less than A.")
    else:
        print("A is equal to B.")
```

3. Write the sum and average of two numbers.

```
BEGIN
	INPUT A, B

	SUM = A + B
	AVERAGE = (A + B) / 2

	OUTPUT "Sum is " + SUM
	OUTPUT "Average is " + AVERAGE
END
```

4. Input 5 numbers and outputs the sum and average of them.

```
BEGIN
	numbers = [] # this is an array
	count = 0
	
	i = 0
	WHILE i < count
		num = INPUT "Enter a number: "
		numbers.append(num)
		i += 1
	ENDWHILE

```

***

# Control structures
Main control structures,
	 1. Sequence
		- This the default execution flow of any program computers will always follow step by step on bare metal.
	 2. Selection
		 - Control structures or conditionals enable a programmer to select a dynamic outcome from the program.
	 3. Repetition/Iteration
		 - Recursion of a block under a conditional enable a programmer to write minimal, reusable code.

 At the end everything executed on a computer will come down to a sequence on computer bare metal, it's just a sugar coat of syntax to make things easier. It is a sequence that is pre-defined will point to the next instruction to be executed.

<label>Lecture 02 - 2022/10/11</label>

## Activity 02
1. Write a pseudocode for a program that takes, 5 input numbers and output the sum and average of the set of numbers.

***

# Introduction to Python

## About Python
Python is a high level programming language that is available for many platforms. It is open source and was created by [Guido van Rossum](https://www.google.com/search?newwindow=1&sxsrf=ALiCzsakMB61auzS8Ttq5AG_8_cF86VNow:1665468984378&q=Guido+van+Rossum&stick=H4sIAAAAAAAAAONgVuLUz9U3MMwwME1-xGjCLfDyxz1hKe1Ja05eY1Tl4grOyC93zSvJLKkUEudig7J4pbi5ELp4FrEKuJdmpuQrlCXmKQTlFxeX5gIACMWaE1cAAAA&sa=X&ved=2ahUKEwjQ18q5w9f6AhVc7nMBHddJD_4QzIcDKAB6BAgnEAE) on 1991. Python is used for almost everything,
	- Web development 
	- Application development
	- Mathematical applications
	- Data mining and machine learning 
	- Scripting

<label>Lecture 03 - 2022/10/18</label>
## Basic Python Usage

### Interacting with the console
The built-in function `print` can be used to print data to the stdout while the inbuilt function `input` can be used to take input from stdin.

### Comments in python
Comments inside code provide context for a third party reader. They are used to document code one has written. Undocumented code is a pain to deal with since it's hard to understand. There are two types of comments in python,
	- Single-line/Inline comments
		They can be written using a '#' symbol. The standard is to leave 2 spaces before the '#' and one space after the '#'.
	- Multiline comments
		Multiline comments can be written by using triple double/single quotes just like a string but without assigning it to a string.
Comments in python also assist type hinting in supports development environments making things much more easier for the developer.

```python

some_variable = 10010123  # This is an inline comment

def some_function():
	"""
	This function does something.
	It takes no arguments and returns no value.
	"""
	pass
```

### Indentation in python
Unlike most other programming languages that use different symbols to encapsulate scopes, python use indentation to take care of scopes.

```python
# global scope
# indentation level 0
x = 0
print(x)  # will not raise an error as 'y' is defined within the same operating scope

def some_function():
	# function scope
	# indentation level 1
	
	y = 1
	print(x)  # will not raise an error as 'x' is defined on it's parent scope
	print(y)  # will not raise an error as 'y' is defined on the same operating scope

print(y)  # this will raise an error as 'x' is defined outside of it's operating scope
```

### Declarations in python
Python is not a type strict language, variables are flexible to contain multiple data types in runtime. Typing is not needed unlike other languages. Some say this is a weak point in python as strict types result in better type hints and cleaner code. One can't assume this variable is this type as it can be changed freely.

Variable references are case sensitive. There are several syntax rules enforced in python when it comes to variable names,
	- Variables can not contain special Unicode characters.
	- Must start with a letter or an underscore.
	- Can not start with a number.
	- Keywords cannot be used as identifiers/variables, however built in functions can be overwritten.



***

