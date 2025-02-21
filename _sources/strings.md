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
# Working with strings

## String indexing and slicing
We have already looked briefly at strings [previously](data_types.md).  Like lists, strings too are of Sequence type in Python, therefore they support slicing, membership operators, 
concatenation, replication and the other utility functions we mentioned in the [Lists](data_structures.md) section.  Instead of data 
items, however, strings are composed of a sequence of characters.  {ref}`string-index` below shows an example of the sequence 
of characters in the string "Hello World!" together with its index positions.  

```{figure} images/string-indexes.png
---
name: string-index
---
Indexes for str "Hello World!"
```

Thus, we can extract characters from a string as in the code below:

```{code-cell} python3
s = "Hello World!"

print("s at index 6 is", s[6])

#Accessing s with a negative index
print("s[-2] value is", s[-2]) 
```
And we can slice a string as below:

```{figure} images/string-slicing.png
---
name: string-slicing
---
String slicing.
```

## Strings are immutable
Strings are immutable, one cannot change the contents of a character in a string.  Trying to 
modify a character in a string will throw an error as shown below:

```{code-cell} python3
:tags: ["raises-exception"]
s[1] = 'a'
```

## String utility functions and methods

More useful functions and methods for strings are listed in {ref}`data-types-table`.  A list of all the String methods 
in Python can be found [here](https://docs.python.org/3/library/stdtypes.html#string-methods).

```{list-table} String utility functions
:header-rows: 1
:name: data-types-table

* - Function
  - Description
* - `len(s)`
  - returns the length of the string `s`.
* - `s.isnumeric()`
  - returns `True` if `s` is a number.
* - `s.lower()`
  - returns `s` in lowercase.
* - `s.upper()`
  - returns `s` in uppercase.
* - `s.count(sub, start, end)`
  - returns the number of times `sub` is present in `s` from `start` to `end` position.
``` 

````{exercise} Joining strings
:label: join-strings

**Level:** {octicon}`star-fill;1em;sd-text-warning` {octicon}`star-fill;1em;sd-text-warning` {octicon}`star;1em;sd-text-warning`

Given a list of `str` objects defined as below:

```{code-block} python
words = ["keep", "calm", "and", "carry", "on"]
```
Join all the `str` objects together and separate them by a space into one `str` object and print it.
The final string should have the following value: "keep calm and carry on"

```{tip}
Use the `join()` String method.  Look at its [documentation](https://docs.python.org/3/library/stdtypes.html#str.join) 
to see how this can be used.
```
````

```{solution-start} join-strings
:label: join-strings-solution
:class: dropdown
```
The `join()` method takes as an argument a list of strings to join together. The separator to use between the different data items in 
`words` is the string we are calling the `join()` method on.
```{code-cell}
words = ["keep", "calm", "and", "carry", "on"]
quote = " ".join(words)
print(quote)
```
```{solution-end}
```

```{exercise} Word counting - splitting strings
:label: split-strings

**Level:** {octicon}`star-fill;1em;sd-text-warning` {octicon}`star-fill;1em;sd-text-warning` {octicon}`star;1em;sd-text-warning`

In this exercise write code that counts and prints the number of words in the famous quote from Star Wars:
 *"May the Force be with you"*
 
```

```{solution-start} split-strings
:class: dropdown
```
To divide strings by a separator, the `split()` string method provides an easy way to do this.  Have a look at the 
[documentation](https://docs.python.org/3.3/library/stdtypes.html?highlight=split#str.split).  If no arguments are passed 
to the `split()` method, all whitespace is removed from the string that called `split()` and a list is returned with the 
separated strings.

```{code-cell} ipython3
sentence = "Your path you must decide"
words = sentence.split()
print(f"There are {len(words)} words in the words list.")
print(words)
```
```{solution-end}
```






