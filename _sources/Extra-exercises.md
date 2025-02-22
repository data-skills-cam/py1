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

# Worksheet 1


```{exercise} For loop
:label: for-words-exercise
:nonumber:
**Level:** {octicon}`star-fill;1em;sd-text-warning` {octicon}`star-fill;1em;sd-text-warning` {octicon}`star;1em;sd-text-warning`

Take the code used to do {numref}`for-exercise` but this time, for each iteration, print the index of the word in list `l` next to the string.
```

```{solution-start} for-words-exercise
:label: for-words-exercise-solution
:class: dropdown
```

```{code-cell} ipython3
l = ["keep", "calm", "and", "carry", "on"]

for i in range(len(l)):
    print(i, l[i])
```
```{solution-end}
```

```{exercise} Odd and even numbers
:label: odd-even
:nonumber:
**Level:** {octicon}`star-fill;1em;sd-text-warning` {octicon}`star-fill;1em;sd-text-warning` {octicon}`star;1em;sd-text-warning`

Modify the code that identifies an [odd or even number](code-continue) to create a list of even numbers, 
and another list of odd numbers.  
```

```{solution-start} odd-even
:label: odd-even-solution
:class: dropdown
```
```{code-cell} ipython3
#initialise empty lists
even, odd = [], []

for i in range(10):          
    if i % 2 == 0:           
        even.append(i)       
        continue             
    odd.append(i)            

print(f"The program has identified {len(even)} even numbers {even}")
print(f"The program has identified {len(odd)} odd numbers {odd}")
```
```{solution-end}
```

````{exercise} Simple calculator
:label: calculator
:nonumber:
**Level:** {octicon}`star-fill;1em;sd-text-warning` {octicon}`star-fill;1em;sd-text-warning` {octicon}`star-fill;1em;sd-text-warning`

Creat a program that works like a simple calculator:
* First, print a user menu that shows the operations available with this calculator:
 *1. Addition  
  2. Subtraction  
  3. Exit*  
* Then ask the user to enter two numbers.
* The calculutaor would then add or subtract these two numbers depending on the operation selected previously.  

```{tip}
The `input()` function is used to read in the user's input from the console.
```
````

```{solution-start} calculator
:label: calculator-solution
:class: dropdown
```

```{code-block}
while True:                                         #1
   print("1. Addition")                             #2
   print("2. Subtraction")                          #3
   print("3. Exit")                                 #4
   print("Choose operation (1-3): ", end="")        #5
   opt = int(input())                               #6
   if opt>=1 and opt<=2:                            #7
      num1 = float(input("Enter first number:"))    #8
      num2 = float(input("Enter second number:"))   #9
   if opt==1:                                       #10
      print("Result:", num1 + num2)                 #11
   elif opt==2:                                     #12
      print("Result:", num1 - num2)                 #13
   elif opt==3:                                     #14
      break                                         #15
   else:                                            #16
      print("No option available")                  #17
   print()                                          #18
                                                    #19
print("Thank you, bye!")                            #20
```
The first line is an **infinite loop** which means that the loop will iterate forever since 
`True` is specified instead of a condition.  This will not be the case however, as in the `if` statement we have a `break` in line 15, which 
stops the loop if the user chooses 3 as an option in the calculator.  Note again the indentation of the code.  The last line is not 
indented under the loop, so it will run after execution of the loop has finished.  

```{solution-end}
```
