---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Data Structures
So far we have dealt with single data items.  But what if we have a large number of data items? Storing each item in a 
separate variable is not efficient and time-consuming.  This is when we use data structures.

:::{card} Data Structures
:class-card: sd-bg-light

{bdg-info}`Programming concept`

Data structures are structures in memory that store and organise data. Essentially it is a collection of data items.
:::
 
The benefits of having multiple data items in a collection makes it easier to perform operations that need to be applied 
on each item in the collection.  Data Structures are also very useful when reading data from files.  This section introduces
different data structures commonly used in Python.  

##  Lists
Lists are one of the built-in data structures in Python.  Lists can contain data items of different data types, but as 
a good practice we normally create lists of the same data type.  Lists are created as a comma-separated list of data items enclosed 
in square-brackets.  Let us create our first list:

```{code-cell} python3
l = [55, 92, 110, 66, 75, 45, 40, 57, 55, 62]
```
The code above creates a variable `l` which references a list in memory that is 10 items long.  Assigning data items to
a list is also known as **list packing**.  

### List index positions and slicing

Each data item has a specified position known as **index position**.  Index positions in Python start from **0**. {ref}`list` below shows an
example of the sequence of data items in list `l` together with their index positions.

```{figure} images/list.png
---
name: list
---
Representation of list `l` in memory and the index positions of its items.
```

A list is a **Sequence type** in Python, and therefore, it can be sliced using the item access operator `[]`.  **Slicing** 
means extracting items from a sequence.  Assuming `seq` is a sequence, in this case of data items, to extract one item from a tuple, specify the index position of that item in  `[]` 
as $seq[index position]$ as in the example below.

(code-list-indexing)=
```{code-cell} python3
#Extract item at index position 2
print("Item at l[2] is", l[2])


#Extract item at index position -2
print("Item at l[-2] is", l[-2])
```

To extract more than one item from a sequence you can either:
* $seq[start:end]$ to extract items from a sequence from a *start* position up to an *end* position (excluding it).
* $seq[start:end:step]$ to extract every *step<sup>th</sup>* item from the sequence starting from the *start* 
position to the *end* position (excluding it).
Below are two examples, A and B, that show these two ways of slicing a tuple.

```{figure} images/list-slicing.png
---
name: list-slicing
---
List slicing.
```

(code-reference-list-slicing)=
Below are code examples of other operations you can do with lists:
```{code-cell} python3
#Extract items from the beginning of the list to index position 2 (excluded).
print("l[:2] is", l[:2])

#Extract items from index position 5 to the end of the list.
print("l[5:] is", l[5:])

#print all items in a list
print("\nPrint all items in list l", l)

# List replication:  replicate contents of a list by a specified number of times
l3 = l * 2
print("\nReplicating list l by 2:", l3)

# List unpacking - place data items of list in separate variables
print("\nList unpacking:")
l4 = ["Alexia", "Cardona", "Python"]
(name, surname, subject) = l4
print("Name is", name)
print("Surname is", surname)
print("Subject is", subject)
```
(test)= 
### Membership operators
Membership operator are used to test for membership in Sequence types.  For lists, the `in` **membership operator** 
returns `True` if a data item in list `l` is equal to `x`, otherwise it returns `False`. The `not in` **non-membership operator** 
does the opposite, it returns `True` if a data item in list `l` is not equal to `x`, otherwise it returns `False`.  The code
below shows an example of using membership operators in lists.

```{code-cell} ipython3
:tags: ["remove-output"]
#Check if number 2 is one of the items of list l
2 in l      #returns False

#Check if number 55 is one of the items of list l
55 in l     #returns True

#Check that 2 is not one of the items of list l
2 not in l  #returns True
```

### Useful operational functions

Below is a list of other useful functions that can be used with list objects.  Note that these functions do not make any changes 
on the lists, but rather they perform a calculation or operation on the data items of the list and return the result.

```{list-table} Useful functions for operations with lists
:header-rows: 1
:name: list-utility-functions2

* - Function
  - Description
  - Example
* - `len(l)`
  - returns the number of data items in a list `l`.
  - `len(l)` returns 10
* - `min(l)`
  - returns the smallest data item in `l`.
  - `min(l)` returns 40
* - `max(l)` 
  - returns the largest data item in `l`.
  - `max(l)` returns 110 
* - `l.index(x)`
  - returns the index of the leftmost index position of data item `x` in list `l` or throws an error if `x` is not present.
  - `l.index(55)` returns 0
* - `l.count(x)`
  - returns the number of times `x` is present in `l`.
  - `l.count(55)` returns 2
``` 

### Modifying lists

List are mutable objects, which means that they can be modified.

```{code-cell} python3
#print contents of l and get id of l
print(l)
print("l is referencing object", id(l), "in memory")

# change the data item at index position 2 of list l
l[2] = 80
print("\nAfter l[2] = 80, l is:", l)
print("l is referencing object", id(l), "in memory")
```
As you can see in the code above, the object id of `l` does not change when the content of `l` is changed.
If you want to make further changes to your list, consider using the utility methods that come with the list object. Below 
are some of the most widely used methods.  

```{list-table} List utility methods
:header-rows: 1
:name: list-utility-methods

* - Function
  - Description
  - Example
* - `l.append(x)`
  - appends data item `x` at the end of list `l`.
  - `l.append(100)`
* - `l.insert(i, x)`
  - insert data item `x` in list `l` at index position `i`.
  - `l.insert(1,44)`
* - `l.extend(iterable)`
  -  extends the list by appending all the items from the `iterable` (`iterable` is another list).
  -  `l.extend([1,2,3])`
* - `l.remove(x)`
  - removes the leftmost occurance of the data item that is equal to `x` or throws an error if `x` is not present in list `l`.
  - `l.remove(55)`
* - `del l[start:end]`
  - The `del` statement removes the data items from start position to end position (excluded) in list `l`.
  - `del l[7:9]`
* - `l.reverse()`
  - reverses the data items in `l`
  - 
* - `l.sort()`
  - sorts the data items of list `l` in ascending order.
  - 
```

```{admonition} Methods vs Functions
:class: tip

We have already seen how to call functions.  Functions are called only by their names, eg. `print()`. Methods are similar 
to functions but they are  defined inside classes or objects, and so they are dependent on them. We will not be going 
into the details of object-oriented programming in this course, but we have already encountered some methods in lists 
that use methods *e.g.,* `l.append(x)`.  Here `l` is an object reference of the `list` class and `append()` is a method 
inside the `list` class.  The dot `.` after `l` is used to access the method associated with the `list` object. In this example, 
a pop-up menu will be shown in PyCharm with the list of all methods associated with `list`. 
```

```{exercise} Exploring lists
:label: lists-utility-exercise

**Level:** {octicon}`star-fill;1em;sd-text-warning` {octicon}`star;1em;sd-text-warning` {octicon}`star;1em;sd-text-warning`
 
Explore lists by:
1. Try the examples in {ref}`list-utility-functions2`.  Check the output of list `l` after running each example.
2. Try the code in the {ref}`test` section.  
3. Try the examples in {ref}`list-utility-methods`. Check the output of list `l` after running each example.

```


