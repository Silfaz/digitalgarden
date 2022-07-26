---
title: "100 days of Python"
---

## 100 days of Python
https://www.udemy.com/course/100-days-of-code/
Dr. Angela Yu

## Basics
For commenting a whole line: **Cmd**+**Shift**+**7** (or **Cmd**+**/**) (**Cmd**+**z** to undo)

### The Python input function
Print function: `print()`
Input function: `input()`

`input` works like this: if I write `print (input ("What's your name?"))` it will print the question and I can put my name in. 

How to store that name in a variable? Just put in a variable name instead of the `print` statement:

1.  name = input ("What's your name?")

Similarly, if I want to turn the answer immediately into a different data type, I can do that together with the `input` command:

`age = int(input ("How old are you?")`

Usually, inputs are strings, so if I just write:

`name = input("What's your name?")`

The input value is stored as a string.

### Understanding data types and how to manipulate strings
`type()` Check the type of a variable, e.g. int, str
`str()` Turn something into a string
`int()` Turn something in to an integer
`round()` Round a number to a specific number of decimal places, e.g. `round(3.5542, 2)`

**F-string:** In front of a string (i.e. in front of the quotes) you type an `f`, then you can include different data types in curly brackets in the quotes. No need to doing `str()` or `int()`, etc.

`print (f"My weight is {weight} kg and my height is {height} m.")`

`variable = variable + 1` is the same as `variable += 1`

Same for -=, *=, /=

E.g. `variable = variable*2` is the same as `variable *=2`

### Control flow and logical operators
`if condition 1:`
`    do A`
`elif condition 2:`
`    do B`
`else: `
`    do C`

`"Silvia".lower()` --> "silvia"
`"Silvia".count("i")` --> 2

Use three single quotes for writing multi-line strings:

`print ('''This`
`is a `
`multi-`
`line string`
`''')``

### Random module
Random number generation with the random module:

`random.randint(1, 10) #Generates random integer between (and including) 1 and 10`
`random.random() #Generates random float between (and including) 0 and (excluding) 1`

Pick a random item from a list:
`random.choice(list_name)`

_Don't try to learn every single function by heart. Instead, when you come across a new thing (e.g. a new data structure), read through the documentation to see what is possible. Then next time when you use it, you can look specific things up._

**When importing modules:** 

either
`import chosen_module`
`print (chosen_module.sentence)`

or
`from chosen_module import sentence`
`print (sentence)`

or
`import chosen_module as mod`
`print (mod.sentence)`

E.g. to import and use the Turtle class from the turtle module, either write:
`import turtle`
`new_turtle = turtle.Turtle()`

or
`from turtle import Turtle`
`new_turtle = Turtle()`

The latter is useful when the class is used often and you don't want to type `turtle.Turtle()` all the time.

It's also possible to import everything from a module and use it as if it was part of the normal environment (i.e. without the module name).
`from turtle import *`

This however can be confusing, since it's often good to know which module a function belongs to.

E.g.
`choice([1,3,4])` looks confusing out of context. But if you write `random.choice([1,3,4])` it's much clearer that it is part of the random module and that a random number is picked from this list.

For long module names, it's also possible to use aliases:

`import turtle as t`
`new_turtle = t.Turtle()`

### Lists
**Lists** store data in a specific order
`fruits = ["Cherry", "Apple", "Pear"]`

To access a specific entry from the list:
`fruits[0]` or `fruits[-1]`

To add an item to the end of an existing list:
`fruits.append("Melon")`

To add several times to the end of an existing list:
`fruits.append(["Strawberry", "Orange", "Peach"]`

`random.choice(list)`
This generates a random choice from a given list.

`str.split()`
Splits a string into separate components based on some defined divider, e.g. a comma.

`str.split(",")`
The result will be a **list** that contains the separate components of the string.

Nested lists contain **lists of lists**. When addressing a specific item in a nested list, you have to first pick the right nested list, then the item in that list, e.g. the first item in the first list would be:
`print (list([0][0])`

Transform a string into a list:
`list(string)`

**in**

The **in** construct is an easy way to test if an element is contained in a collection, e.g. in a list.

`list = ["Silfa", "Duncan", "Laika"]`
`if "Silfa" in list:`
`    print ("yay")`

### Loops
`letters = ["a", "b", "c", "d"]`
`for letter in letters:`
`   print (letter)``

NB: The item (here `number`) in a for loop does **NOT** count from 0 to i, but instead takes the value of the first item in the list (e.g. `"a"`) and takes on that value. This means, that to have some kind of **counting variable** that is first set to 0 (outside the loop) and then increases with each round inside the loop, you have to do the following:
`count = 0`
`for letter in letters:`
`    print (letter)`
`    count += 1``
Then with each round through the loop, `count` will increase by 1, and will in the end have the same value as items in `letters`.

For loops are often used to loop through lists, but you can also loop through ranges of items that are not lists.

**for loops and the** `**range()**` **function**

`for number in range (a, b):`
`    print (number)`
_NB: a is included, b is not_

The step size can also be changed, e.g. to increase the numbers by 3, type:
`range(1, 100, 3)`

**So there are 2 types of for loops:**
type 1

`for item in list _of_items:`
`    #do something to each item`

type 2
`for number in range(a,b):`
`    #do something``

**_When to use a for and when a while loop?_**

**For** loops are great when you iterate over something, and you want to do something with each thing you iterate over. E.g. iterating through a list.

  

**While** loops are used when you just want to carry out some sort of functionality many times until a condition is met. Don't care about what number in a sequence you're in, which item in a list you're iterating through, etc.

While loops are a bit more dangerous than for loops. In for loops you always have an upper bound, but while loops will continue running until the condition evaluates to `FALSE`. That can lead to infinite loops.

A good thing to do when you don't know why you get an infinite loop, simply `print()` the condition inside the loop and check what's happening.

**While loop**
A loop that keeps on going while a condition is `TRUE`.

`while something_is_true:`
`    #do a thing, then test the condition again, etc.`

Once the condition evaluates to FALSE, the while loop is skipped.

Example of how a while loop can be used:
`count = 6`
`while count > 0:`
      `print ("Hello!")`
      `count -= 1   #this decreases the` `number of counts by one every time` `the loop runs`
  
While loops can also be used while a condition is `FALSE`. For that, use this syntax:

`while not some_condition_that_is_true:`
`    #do something`

This means the loop runs while the condition is `FALSE`, but as soon as it evaluates to `TRUE`, we drop out of the loop.

A good way to **include a check in a while loop** is to set a variable to `True` (or `False`) before the while loop starts. Then set the while loop to run WHILE the `variable == True`. Inside the while loop, something makes the variable either remain `True` or switch to `False`. In case of False, the while loop will stop.

A good way to **increase something or build something up in a For loop** is to set an empty string or an empty list outside of the for loop first. Then inside the for loop, in every turn something is added to the string or list, adding up to the final string or list when the for loop is finished.

### Dictionaries
Dictionaries are useful if you want to associate labels with each value. Lists are better if you are storing similar data, such as a list of proces or names, where you cannot label each value.

`dictionary1 = {`
`   key1: value1,`
`   key2: value2,`
`   key3: value3,`
`   }

To get a value back:
`dictionary1[key2]`

To add an entry to the dictionary:
`dictionary1[key4] = value4`

Similar to lists and strings, it's often useful to start with an _empty_ dictionary, and then later on add to the dictionary.
`dic_new = {}`

When looping through a dictionary, usually the **key** will be picked out:

`for key in dictionary1:`
`   print (key)`

If you want to access a specific **value** in a dictionary (e.g. when looping through the dictionary):

`for key in dictionary1:`
`    print (dictionary1[key])``

**Nested dictionaries**
The nested dictionaries don't need to be the same size as the outer dictionaries. They can also include lists, strings, numbers, etc.

Lists are ordered and are accessed by the position inside the list. Dictionaries are NOT ordered.

Dictionaries (or lists) are like folders. They can contain values, but they can also contain other dictionaries (or lists).

A **_dictionary that contains a list_** looks like this:

`travel_log = {`
`   "France": ["Paris", "Lille", "Dijon"],`
`    "Germany": ["Berlin", "Hamburg", "Stuttgart"],`
`    }`

  
A **_dictionary that contains a dictionary_** looks like this:
`travel_log = {`
      `"France": {"cities_visited": ["Paris", "Lille", "Dijon"], "total_visits": 12},`
      `"Germany": {"cities_visited": ["Berlin", "Hamburg", "Stuttgart"], "total_visits": 5},`
`}`

And a **_list that contains dictionaries_** looks like this:
`travel_log = [`
`{`
`"country": "France", `
`"cities_visited": ["Paris", "Lille", "Dijon"], `
`"total_visits": 12,`
` },`
` {`
`"country": "Germany",`
`"cities_visited": ["Berlin", "Hamburg", "Stuttgart"],`
` "total_visits": 5,`
` },`
` ]`

To get **values** from a dictionary, type the variable for the dictionary, followed by the key in square brackets:
`dictionary["name"]`

To get the **keys** from a dictionary, you can turn the keys into a list, and then refer to an item in this list. NB: items in a list are ordered, while items in a dictionary are not!
`keys_list = list(dictionary)`

To get **values from a dictionary of lists**, type the variable for the dictionary, the index of the entry in question, followed by the key in square brackets:
`dictionary[0]["name"]`

#### Generate dictionary from a list
Several options:
- `dict.fromkeys()` Used to create a dictionary from a list. It accepts a list of **keys** that you want to turn into a dictionary. Optionally, you can specify a value you want to assign to every key. You cannot set individual values for each item in the dictionary. 
	E.g. 
	`fruits = ["Apple", "Pear", "Banana"]`
	`fruit_dict = dict.fromkeys(fruits, "In stock")`
If we did not specify a value in our code, the default value for the keys in the dictionary would be `None`. 
- Dictionary comprehension: Creates a new dictionary from an existing list. You can specify different valuues for each key in the dictionary. 
	E.g.
	`fruits = ["Apple", "Pear", "Banana"]` 
	`fruit_dict = { fruit: "In stock" for fruit in fruits }
	The dictionary comprehension runs through each item in the list `fruits`. We then add an item to our new dictionary for each fruit in our list. 
- `zip()` Converts (merges) two or more lists into a list of tuples. You can use the `dict()` method to convert the list of tuples into a dictionary. This way, one list can become the keys of the dictionary, and the other the values, e.g. if you have one list with fruits, and the other with the price of these fruits. 
	`fruits = ["Apple", "Pear", "Banana"]`
	`prices = [3.5, 4.0, 2.1]`
	`fruit_dict = dict(zip(fruits, prices))`

#### Loop (iterate) over a dictionary
Dictionaries contain an `__iter__()` method that iterates over the keys. this method is automatically called when you put a dictionary into a `for` loop.
`for key in a_dict: print (key)` 

If you want access to the values, use the indexing operator `[]` with the dictionary and its keys:
`for key in a_dict: print (a_dict[key])`  

When you're working with dictionaries, it's likely that you'll want to work with both the keys and the values. One of the most useful ways to iterate through a dictionary is by using `.items()`, which is a method that returns a new view of the dictionaries items. It's a dynamic view, meaning that if the dictionary changes, the view reflects these changes. 
Views can be iterated over to yield their respective data, so you can iterate through a dictionary in Python by using the view object returned by `.items()`: 
`for item in a_dict.items(): print(item)`--> returns tuples of the key-value pairs


If you just need to work with the keys of a dictionary, then you can use `.keys()`, which is a method that returns a new view object containing the dictionary's keys. To iterate through a dictionary by using `.keys()`, you just need to call `.keys()` in the header of a `for` loop:
`for key in a_dict.keys(): print (key)` 
Similarly, you can use `.values()` to iterate through values. 
Both `.keys()` and `.values()` can be used to check if a key or value is present in a dictionary by using `in`: `"apple" in a_dict.values()`. 

#### Modifying values and keys
You'll need to use the original dictionary! 

#### Filtering items
Sometimes you'll want to create a new dictionary from an existing dictionary, that only stores the data that satisfies a given condition. You can do this with an `if` stateent inside a `for` loop:
`a_dict = {"one": 1, "two": 2, "three": 3, "four": 4}``
`new_dict = {}`
`for key, value in a_dict.items():`
`if value <= 2: new_dict[key] = value`
`#new_dict = {"one": 1, "two", 2}` 


### Tuples
`my_tuple = (1, 2, 3)` --> similar to list

Items in a tuple are ordered (as in a list) and are accessed by indexing with square brackets.

What's the difference from a list? A tuple's values can't be changed once it's created (i.e. **_immutable_**).

When do you want to use a tuple? When creating something that shouldn't be changed or is protected from accidental change (e.g. the colour scheme of a website).

When you want to change a tuple's values, you can convert it into a list by writing:  
`list(my_tuple)`
and then you can change the values as you would in a list.

**Creating tuples:** 
`new_tuple = (first_item, second_item, third_item)`
--> separated by commas, and in round brackets

To access tuples, use same notation as for lists:
`new_tuple[0] #first_item`


## Functions
**Functions**
Python has built-in functions, e.g. `int()`, `range()`, `print()` or `round()`.

Creating your own functions:
`def my_function():`
  `      content of function`

To call the function:
`my_function()`

**Functions with inputs**

`def my_function(something):`
`    #Do this with something`
`    #Then this `
`    #And finally this with something`

A function can have several parameters:
`def my_function (param1, param2):`

This called **positional arguments**
`def my_function (a, b, c):`
`    #Do this with a`
`    #then do this with b`
`    #then this with c`

In comparison with keyword arguments the order doesn't matter. When a function is called, the name of the parameter is used, together with the argument for it:

`my_function (a=1, b=2, c=3)`

Since order doesn't matter, we could also write:

`my_function (b=2, c=3, a=1)`

**_Functions with outputs_**

Can be simple or take inputs (arguments). Inside the function, the keyword `return` is used to "transfer" a result/output to the _outside_ of the function, so it can be used further.

`def my_function():`
`result = 2*3`
`return result`

After the `return` keyword, the function is exited, and anything that would come after the `return` keyword in the function will not be executed. This can be used to return the function early if needed (e.g. check with an `if` statement if some condition is true, and then just use the `return` keyword to exit out of the function).

**Different types of functions:**
  
**_Simple functions_**
Very simple, without any parameters. Just reduced complexity by reducing the amount of code you need to write (e.g. if there is a recurring task).

`def my_function():`
`#do this`
`#then do this`
`#finally do this`

To call this function:
`my_function()`

**_Functions with inputs_**
Functions with parameters take an input that gets passed into the function when the function is called. This allows us to modify what the function does, depending on what input was passed in.

`def my_function(something):`
`#do this with something`
`#then do this`
`#finally do this`

To call this function:
`my_function(123)`


**_Docstrings_**
With docstrings, you can include a comment or little explanation with your newly created function about what it does and what it takes as input. Docstrings must be placed in the first line of the function and have to be encased in triple quotation marks. They can run over several lines.

`def some_function(a, b):`
`"""This function takes inputs a and b and does something to them, `
`returning something else."""`

**Keyword arguments**
Especially for functions you haven't written yourself, it's really useful to write keyword arguments instead of positional arguments when calling the function.

With keyword arguments, you specify which argument you are referring to.
`def function1 (a, b, c):`
`#some function text`
`function1(a=13, b=44, c=0)`

**Recursion** 
= calling a function inside itself
You can also take the output of one function call as an input for another function call. This is very useful for complex functions.

**Useful functions:**

`sum([list])` gives a sum of all items in the list
`random.choice([list])` picks a random item from a list (requires to import the random package first)

Global variables are by convention written in all caps.

To exit a function, simply use the `return` keyword.

**Higher order function**
A function that can work with other functions. E.g. it can take another function as an input and work with it inside the body of the function.

When passing a function as an argument to another function, don't use the paranthesis at the end. E.g.
`function_a (function_b)`


## Debugging
1. Describe the problem
2. Reproduce the bug
3. Play computer
4. Fix the errors
5. Print is your friend
6. Use a debugger
7. Take a break
8. Ask a friend
9. Run your code often
10. Ask Stackoverflow

To access and change a global variable inside a local environment, e.g. a function, you have to write `global` + variable name first.

For example:
`some_variable = 4`
`def increase_something():`
`global some_variable`
`some_variable += 1``


## Object-oriented programming (OOP)
**OOP analogy:**
You come to a foreign country and don't know the language, don't know the city and don't have local money, but you want your clothes dry-cleaned. Instead of doing it yourself, you ask the hotel staff to do it, who know the language, the city and have local money.
`hotel.dry_clean_clothes()`


Objects have things they HAVE and things they DO.
Things they HAVE = **_attributes_**
E.g.
`is_holding_plate = True`
`tables_responsible = [4, 5, 6]`

Things they DO = **_methods_**
Methods are functions specific for an object
E.g.
`def take_order(table, order):`
`#takes order to chef`
`def take_payment(amount):`
`#add money to restaurant``

### Classes
Classes are _blueprints_ for objects.
Classes are usually written in Pascal case, i.e. every word beginning is capitalized
E.g.
`car = CarBlueprint()`

To leave a class or function empty (for now), you can use the keyword `pass` to avoid "indent error" messages.

#### init function
**Constructor** = part of the class that specifies what should happen when our object is constructed (= initializing an object). Variables and counters are set to their starting values.

Use special function `__init__ (self)` to initialize the attributes.

The init function is going to be called every time a new object from this class is created.

In addition to the parameter self, there can be as many parameters as you want in the brackets after __init__. These parameters get passed in when a new object is constructed. These parameters can then be used to set an object's attributes.


To have a default value for an attribute, instead of setting it equal to one of the parameters of the init function, set it to a value in the init function (not the parameters!).

e.g.
`def __init__ (self, user_id, username):`
`self.user_id = user_id`
`self.username = username`
`self.followers = 0`

This way the new object has new_object.followers set to 0 by default.

Example of init function:
`class Car:`
`def __init__(self, seats):`
`self.seats = seats`

The number of seats specificied when a new object of this class is initialized gets passed to that object as an attribute.

`new_car = Car(5)` --> this will set the attribute new_car.seats to 5.

There can be many parameters in the init function. However, it means that whenever you create a new object from this class, you MUST provide all these pieces of information for the new object.

#### Making a new class
`class User:`
`#add functions, etc.`

`user_1 = User()` to make a new instance of the class

`user_1.username = "Silfa"` to create a new attribute for the object. An attribute is a variable that is associated with an object.

But for attributes that all new instances should have in common, it's better to include them in the constructor.

#### Methods in classes
Methods = what the object DOES, i.e. a function that the object has.

Methods can use `self.` attributes of objects.

To call the method, use the normal dot notation with brackets after the method, e.g.
`user_1.start_game()`

Methods in classes always need to have a `self` parameter as the first (and sometimes only) parameter. This means that when the method is called, it "knows" the object that called it.

`def new_method(self):`
`self.followers += 1`

The `self` keyword is a way to refer to the object that is being created from a class.

We can use the class name inside an object to tap into the class.

For example we can create a list of objects by initiating new instances of a class inside a loop and filling a list with these new objects. These objects have all the attributes that are defined in the class constructer, and these attributes can be accessed with dot notation.


When inside a class, and calling one of the functions inside one of the other functions, you have to use `self.` before the function name.

E.g.
`def function_using_another_function(self, input, something):`
`self.previous_function(attribute1, attribute2)`
`...`


Different **instances** of classes can have different **states**. E.g. Turty and Timmy can be different instances of the class Turtle(), and they can have different states, e.g. `turty.color = green` and `timmy.color = purple`. 

## Interesting modules and other things

**colorgram** is a Python library that lets you extract colours from images.

