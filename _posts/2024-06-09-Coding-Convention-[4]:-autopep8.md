---
layout: post
date: 2024-06-09
title: "Coding Convention [4]: autopep8"
tags: [coding-convention, code-formatter, autopep8, PEP8, ]
categories: [Coding Convention, ]
---



## Prerequsites


---


**[1]** [**Coding-Convention-1-Code-Formatter**](https://rebedy.github.io/posts/Coding-Convention-1-Code-Formatter/)


**[2]** [**Coding-Convention-2-Black**](https://rebedy.github.io/posts/Coding-Convention-2-Black/)


**[3]** [**Coding-Convention-3-Prettier**](https://rebedy.github.io/posts/Coding-Convention-3-Prettier/)



## [**autopep8**](https://pypi.org/project/autopep8/)


---


![0](/assets/img/2024-06-09-Coding-Convention-[4]:-autopep8.md/0.png)_https://all-share-source-code.tistory.com/80_


Module that automatically corrects Python code to conform to the **PEP8 convention**.

- **PEP8** is the official Python style guide.


### 1. Install and set autopep8

- **Installation**
	- **Extension > Search** **`autopep8`** **> Install** **`autopep8`** **extension**
- **Setting**
	- **Settings (** **`ctrl + ,`****) > Search** **`python formatting`** **> Find** **`Python > Formatting: Provider`** **> Set to** **`autopep8`**


### 2. When installation does not work / is not in the options


If **autopep8** does not appear in the python formatting options, you need to change the settings.


When other python code formatter (**Prettier**) is already set as the default so it cannot be set as **`autopep8`**.


![1](/assets/img/2024-06-09-Coding-Convention-[4]:-autopep8.md/1.png)



#### 2-1. Change setting in `settings.json`


The formatter can only be changed in python format files this way.

- Settings (**`Ctrl + Shift + P`****)** > Enter **`open user settings`** > Go to **`Preferences: Open User Settings (JSON)`** > Add code below in between the braces > Save > Restart VSCode


{% raw %}
```json
{
...
    "[python]": {
      "editor.formatOnType": true,
      "editor.defaultFormatter": "ms-python.autopep8",
      "editor.formatOnSave": true
    },
...
}
```
{% endraw %}




#### 2-2. Change default formatter


We gotta be careful with this one. ⚠️ The formatter is applied as **autopep8** in all files. So if you are working on the other developments simultaneously, the formatting method may be messed up! If you are working on python ONLY then this will be fine. 🙂

- Settings > Search **`Default Formatter`** > Choose **`autopep8`**


### 3. Set to automatically run on the save


Once it’s activated, the formatter will run automatically when the file is saved. If not set, you must run the formatter manually.

- **Settings (** **`ctrl + ,`****) > Search** **`format on save`**  **> Activate > Restart VSCode**

![2](/assets/img/2024-06-09-Coding-Convention-[4]:-autopep8.md/2.png)



## [PEP8](https://peps.python.org/pep-0008/)


---


Code conventions differ across programming languages. For Python, the convention is known as **PEP8**.


The **autopep8** package offers automatic formatting. However, it's not flawless, so it's beneficial to familiarize yourself with it before use.



### 1. Naming Convention


| **Types**    | **Naming Convention**                                                                                                                                           | **example**                                     |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| **Function** | Use a **lowercase** word/words. Use underscores to separate works for readability.                                                                              | function, my_function                           |
| **Variable** | Use a **lowercase** single letter, word/words. Use underscores to separate works for readability.                                                               | x, var, my_variable                             |
| **Class**    | Use [**camel case or Pascal case**](https://en.wikipedia.org/wiki/Camel_case). Start each word with a capital letter and don’t separate words with underscores. | Model, MyClass                                  |
| **Method**   | Use a lowercase word/words. Separate words with underscores to improve readability.                                                                             | class_metho                                     |
| **Constant** | Use an **uppercase** single letter, word/words. Use underscores to separate works for readability.                                                              | CONSTANT, PYTHON_CONSTANT, PYTHON_LONG_CONSTANT |
| **Module**   | Use a **short**, **lowercase** word/words. Use underscores to separate works for readability.                                                                   | module.py, my_module.py                         |
| **Package**  | Use a **short**, **lowercase** word/words. Don’t separate words with underscores.                                                                               | package, mypackage                              |

undefined

### 2. **Code Layout**



#### 2-1. Blank Lines


**(1) Surround top-level functions and classes with** **two blank lines****.**



{% raw %}
```python
class First:
    pass


class Second:
    pass


def top_level_function():
    return None
```
{% endraw %}



**(2) Surround method definitions inside classes with a** **single blank line****.**



{% raw %}
```python
class ClassWithMethods:
		def __init__(self):
				self.a = 1

    def first_method(self):
        return self.a

    def second_method(self):
        return None
```
{% endraw %}



**(3) Use blank lines infrequently inside functions to indicate clear steps.**



{% raw %}
```python
def calculate_variance(numbers):
    sum_numbers = 0
    for num in numbers:
        sum_numbers = sum_numbers + num
    mean = sum_numbers / len(numbers)

    sum_squares = 0
    for num in numbers:
        sum_squares = sum_squares + num**2
    mean_squares = sum_squares / len(numbers)

    return mean_squares - mean**2
```
{% endraw %}


- Separated the logical steps with a blank line in between them to improve readability.
- A blank line before the `return` statement helps us to clearly see what the function returns.


#### **2-2. Maximum Line Length and Line Breaking**

- PEP 8 suggestion is limited to 79 characters.

**(1) Line continuation within** [**parentheses, brackets, or braces**](https://en.wikipedia.org/wiki/Bracket)



{% raw %}
```python
def function(arg1,
						 arg2,
             arg3,
             arg4):
    return None
```
{% endraw %}



**(2) Backslashes (****`\`****) to break lines instead**



{% raw %}
```python
from package import example1, \
    example2, example3
```
{% endraw %}



**(3) Breaking before a binary operator**



{% raw %}
```python
total = (first
         + second
         - third)
```
{% endraw %}


- Breaking _after_ a binary operator is not recommended. ⚠️


### 3. Indentation



#### 3-1. Tabs vs Spaces

- YOU SHOULD USE SPACES INSTEAD OF TABS WHEN INDENTING YOUR CODE. 🚧


{% raw %}
```python
def mixed_indentation(greeting=True):
····if greeting:
········print("Hello")
⇥   print("World")  # Indented with a tab.

mixed_indentation()
```
{% endraw %}


- On the right bottom in VSCode, you can check your setting for indentation!

![3](/assets/img/2024-06-09-Coding-Convention-[4]:-autopep8.md/3.png)

- If you click the `Space:4` (`Select Indentation`) above, you can change the number of Spaces for indentation from `Indent Using Spaces` or change the indentation of the script from `Convert Indentation to Spaces`.

![4](/assets/img/2024-06-09-Coding-Convention-[4]:-autopep8.md/4.png)

- If you’re using Python 3 and run code that mixes tabs and spaces, then you’ll get an error:


{% raw %}
```bash
$ python mixed_indentation.py
  File "./mixed_indentation.py", line 4
    print("World")  # Indented with a tab.
TabError: inconsistent use of tabs and spaces in indentation
```
{% endraw %}




#### **3-2. Indentation Following Line Breaks**

- There are two styles of indentation.

**(1) Align the indented block with the opening delimiter**



{% raw %}
```python
def function(arg_one, arg_two,
             arg_three, arg_four):
    return arg_one
```
{% endraw %}



**(2) Hanging indent**

- This is a typographical term meaning that every line but the first in a paragraph or statement is indented.


{% raw %}
```python
var = function(
    arg_one, arg_two,
    arg_three, arg_four)
```
{% endraw %}


- Note that if you’re using a hanging indent, there must not be any arguments on the first line.


#### 3-3. T**he Closing Bracket**


PEP 8 provides two options for the position of the closing bracket in implied line continuations:


**(1) Line up the closing bracket with the first non-whitespace character of the previous line:**



{% raw %}
```python
list_of_numbers = [
    1, 2, 3,
    4, 5, 6,
    7, 8, 9
    ]
```
{% endraw %}



**(2) Line up the closing bracket with the first character of the line that starts the construct:**



{% raw %}
```python
list_of_numbers = [
    1, 2, 3,
    4, 5, 6,
    7, 8, 9
]
```
{% endraw %}




### 4. Comments



#### 4-1. Block Comments


PEP 8 provides the following rules for writing block comments:

- Indent block comments to the same level as the code that they describe.
- Start each line with a `#` followed by a single space.
- Separate paragraphs by a line containing a single `#`.


{% raw %}
```python
for number in range(0, 10):
    # Loop over `number` ten times and
    # print out the value of `number`
    # followed by a newline character.
    print(i, "\n")
```
{% endraw %}




#### 4-2. Line Comments

- Use inline comments sparingly.
- Write inline comments on the same line as the statement they refer to.
- Separate inline comments from the statement by two or more spaces.
- Start inline comments with a `#` and a single space, like block comments.
- Don’t use them to explain the obvious.


{% raw %}
```python
x = 717  # This is an inline comment
```
{% endraw %}



**(1) Leave it to Naming Convention!** 📛



{% raw %}
```python
# Don't
x = "Dyan Lee"  # Student Name

# Do
student_name = "Dyan Lee"
```
{% endraw %}



**(2) Don't make obvious comments that clutter the code!** 🧵



#### 4-3. Documentation Strings


Documentation strings, also known as [docstrings](https://realpython.com/documenting-python-code/#documenting-your-python-code-base-using-docstrings), are strings enclosed within either triple double quotation marks (`"""`) or triple single quotation marks (`'''`).



{% raw %}
```python
# documented_module.py
"""This is a docstring."""

# ...
```
{% endraw %}



You can access the docstring of an object using its `.__doc__` attribute or the `help()` function:



{% raw %}
```python
>>> import documented_module

>>> documented_module.__doc__
'This is a docstring.'

>>> help(documented_module)
Help on module documented_module:

NAME
    documented_module - This is a docstring.

FILE
    ./documented_module.py
```
{% endraw %}



They typically appear on the first line of any function, class, method, or module. You use docstrings to explain and document a specific block of code.


**(1) A one-line docstring**

- you can keep the whole docstring on the same line:


{% raw %}
```python
def adder(a, b):
    """Add a to b."""
    return a + b
```
{% endraw %}



**(2) When the implementation is more complex.**

- Start with an overview description in the first line.
- Then use more text to document the code object and include a description of the arguments and return value.
- Finally, put the three quotation marks that end a multiline docstring.


{% raw %}
```python
def preprocess(self, dimg: np.ndarray):
		"""
	  This function preprocesses the probe image and returns the
	  preprocessed image data.
	
	  Parameters
	  ----------
	  dimg (np.ndarray): a numpy ndarray of probe image from web cam.
	
	  Returns
	  ----------
	  id_data (np.ndarray): a numpy ndarray of preprocessed image data.
	  """
	  id_data = Image.fromarray(dimg).convert("L").resize((256, 256))
	  id_data = self.adjust_gamma(np.array(id_data))
	  id_data = (id_data / 255).astype(np.float32)
	  id_data -= self.mean
	  id_data *= self.denominator
	  id_data = np.expand_dims(np.expand_dims(id_data, 0), 0)
	
	  return id_data
```
{% endraw %}




### **5. Whitespace in Expressions and Statements**



#### 5-1. **Whitespace Around Binary Operators**


According to PEP 8, we need to surround the following binary operators with a single space on either side for best readability.

- [Assignment operators](https://realpython.com/python-assignment-operator/): `=`, `+=`, `=`, and so forth
- **Comparisons**: `==`, `!=`, `>`, `<`. `>=`, `<=`, `is`, `is not`, [`in`](https://realpython.com/python-in-operator/), and `not in`
- **Booleans**: [`and`](https://realpython.com/python-and-operator/), [`not`](https://realpython.com/python-not-operator/), and [`or`](https://realpython.com/python-or-operator/)

But when you use the equal sign (`=`) to assign a default value to an argument, don’t surround it with spaces! 🚧



{% raw %}
```python
# ✅ Recommended
def function(default_parameter=5):
    # ...


# ❌ Not recommended
def function(default_parameter = 5):
    # ...
```
{% endraw %}



**(1) Operator in a statement**



{% raw %}
```python
# ✅ Recommended
y = x**2 + 5
z = (x+y) * (x-y)

# ❌ Not recommended
y = x ** 2 + 5
z = (x + y) * (x - y)
```
{% endraw %}



**(2)** **`if`** **statements with multiple conditions**



{% raw %}
```python
# ✅ Recommended
if x>5 and x%2==0:
    print("x is larger than 5 and divisible by 2!")

# ❌ Not recommended
if x > 5 and x % 2 == 0:
    print("x is larger than 5 and divisible by 2!")

# ❌ Not recommended
if x >5 and x% 2== 0:
    print("x is larger than 5 and divisible by 2!")
```
{% endraw %}



**(3) Slices (colons as binary operators)**



{% raw %}
```python
# ✅ Recommended
a_list[3:4]

# Treat the colon as the operator with lowest priority.
a_list[x+1 : x+2]

# In an extended slice, you must surround both colons
# with the same amount of whitespace.
a_list[3:4:5]
a_list[x+1 : x+2 : x+3]

# You omit the space if you omit a slice parameter.
a_list[x+1 : x+2 :]
```
{% endraw %}




#### 5-2. T**o Avoid Adding Whitespace**


PEP 8 provides clear examples of where not to use whitespace.


**(1) Trailing whitespace**


Avoid adding whitespace at the end of a line, known as **trailing whitespace**. It's invisible and can cause noisy diffs when using [version control](https://realpython.com/python-git-github-intro/), and may even lead to errors in certain situations.


Example of trailing whitespace.



{% raw %}
```bash
# trailing_whitespace.py
x = 1 + 2 + \ 
    3 + 4

  
$ python trailing_whitespace.py
  File "trailing_whitespace.py", line 1
    x = 1 + 2 + \ 
                 ^
SyntaxError: unexpected character after line continuation character
```
{% endraw %}



**(2) Inside of parentheses, brackets, or braces**



{% raw %}
```python
# ✅ Recommended
numbers = [1, 2, 3]

# ❌ Not recommended
numbers = [ 1, 2, 3, ]
```
{% endraw %}



**(3) Before a comma, semicolon, or colon**



{% raw %}
```python
x = 5
y = 6

# ✅ Recommended
print(x, y)

# ❌ Not recommended
print(x , y)
```
{% endraw %}



**(4) Before the opening parenthesis**



{% raw %}
```python
def double(x):
    return x * 1

# ✅ Recommended
double(1)

# ❌ Not recommended
double (1)
```
{% endraw %}



**(4) Between a trailing comma and a closing parenthesis**



{% raw %}
```python
# ✅ Recommended
a_tuple = (1,)

# ❌ Not recommended
a_tuple = (1, )
```
{% endraw %}



**(5) To align assignment operators**



{% raw %}
```python
# ✅ Recommended
var_1 = 1
var_2 = 2
some_long_var = 3

# ❌ Not recommended
var_1         = 1
var_2         = 2
some_long_var = 3
```
{% endraw %}




## References


---

- [https://hangbok-archive.com/development/devkit/autopep8-설치/](https://hangbok-archive.com/development/devkit/autopep8-%EC%84%A4%EC%B9%98/)
- [https://realpython.com/python-pep8/](https://realpython.com/python-pep8/)
