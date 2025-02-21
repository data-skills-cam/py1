# Help
The best place to find help in Python is using the [Python documentation](https://docs.python.org/3/) which contains 
information about the Python syntax and about its functions and libraries.  It also contains a tutorial and other user 
guides. The Python documentation is especially helpful when you are not familiar with a function, and so you would like to 
understand how to use it. 

```{figure} images/python-doc.png
:width: 70%
:name: python-doc

Searching the Python documentation for the `abs()` function.
```

In the example above in {ref}`python-doc`, we would like to understand how to use the function `abs()`.  We first search for the `abs` function 
in the Python document *(panel A)*.  This returns a list of results.  The first item in the results returned is what we are looking 
for as it says that `abs` is a built-in function *(panel B)*.  Upon clicking on that link we are redirected to the Python documentation
about `abs()` *(panel C)* which provides more information about that function.  Note that in the documentation it is defined as 
`abs(x)`.  `x` here is a **parameter**, which essentially means that it is a variable in the function definition.  This should be 
distinguished from an argument which is the actual value passed to a function (in `abs(-20)` -20 is the argument).

Another way to get help on functions is via the `help()` function.  To access this form of help, type `help(abs)` in the 
console.  This returns a shorter definition of `abs()` but most of the time this is enough.  Essentially you can pass 
the function you want to know about as an argument to `help()`.

If none of these options was not enough to help you understand what you are looking for, there are several Python resources 
on the internet that might have more information and provide examples.  A simple search sometimes would do the trick!
