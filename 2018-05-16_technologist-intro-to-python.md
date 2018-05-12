
Mostly pinched adapted ideas from software carpentry, should be a half hour presentation. Unfortunately, a presentation and not an interactive programming session, but will have questions throughout to keep people awake.

This is mostly an aide-memoire, all will be live coded and this will be printed out

# Things that will be covered

- variables
- printing
- loops
- lists
- conditionals
- importing (maybe numpy mean?)

## variables and printing


```python
3 + 5
```




    8




```python
12 / 7
```




    1.7142857142857142




```python
weight_kg = 70
```


```python
print(weight_kg)
```

    70



```python
today = "Wednesday"

print("Today is", today)
```

    Today is Wednesday



```python
print("weight in pounds:", 2.2 * weight_kg)
```

    weight in pounds: 154.0


Can change a variable's value after it's been assigned


```python
weight_kg = 75
print("New weight is:", weight_kg)
```

    New weight is: 75


If we imagine the variable as a sticky note with a name written on it, assignment is like putting the sticky note on a particular value


```python
weight_lb = weight_kg * 2.2
weight_kg = 5
print("Weight in kg:", weight_kg)
print("Weight in lb:", weight_lb)
```

    Weight in kg: 5
    Weight in lb: 165.0


## Loops

Benefit of computers is that they can do the same thing again and again without making mistakes or getting bored


```python
word = "lead"
```


```python
print(word[0])  # explain zero index
```

    l



```python
print(word[0])
print(word[1])
print(word[2])
print(word[3])
```

    l
    e
    a
    d


- Bad because it's a lot of typing, coders are lazy
- fragile, longer string we have to change it or it misses, shorter and it breaks


```python
word = "tin"
print(word[0])
print(word[1])
print(word[2])
print(word[3])
```

    t
    i
    n



    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-12-3fe119f6f422> in <module>()
          3 print(word[1])
          4 print(word[2])
    ----> 5 print(word[3])


    IndexError: string index out of range



```python
word = "lead"

for letter in word:
    print(letter)
```

    l
    e
    a
    d



```python
word = "oxygen"

for letter in word:
    print(letter.upper())
```

    O
    X
    Y
    G
    E
    N



```python
word = "oxygen"

for peanut in word:
    print(peanut.upper())
```

    O
    X
    Y
    G
    E
    N



```python
counter = 0

for vowel in "aeiou":
    counter = counter + 1

print("There are", counter, "vowels")
```

    There are 5 vowels


## Lists


```python
odds = [1, 3, 5, 7]
print("odds are:", odds)
```

    odds are: [1, 3, 5, 7]



```python
print(odds[0])  # what do you think this does
```

    1



```python
print(odds[1])  # what do you think this does
```

    3



```python
print(odds[-1]) # what about this?
```

    7



```python
print("first:", odds[0])
print("last:", odds[-1])
```

    first: 1
    last: 7



```python
for number in odds:
    print(number)
```

    1
    3
    5
    7



```python
## if have time drop in a list of names

cake = ["flour", "sugar", "butter", "eggs"]

for ingredient in cake:
    print(ingredient)

carrot_cake = cake + ["carrots"]

for ingredient in carrot_cake:
    print(ingredient)
```

    flour
    sugar
    butter
    eggs
    flour
    sugar
    butter
    eggs
    carrots


## conditionals


```python
print(5 > 10)
print(2 < 5)

if 5 > 10:
    print("5 is greater than 10?")

if 2 < 5:
    print("2 is smaller than 5")
```

    False
    True
    2 is smaller than 5



```python
if True:
    print("It's True")

if False:
    print("It's False")
```

    It's True



```python
print(4 in [1, 2, 4])
```

    True



```python
num = 37
if num > 100:
    print('greater')
else:
    print('not greater')
print('done')  # what do you think this will show?
```

    not greater
    done



```python
num = 66
if num > 100:
    print('greater than 100')
elif num > 50:
    print('greater than 50')
elif num == 50:
    print('is 50')
else:
    print('not greater')
print('done')  # what do you think this will show?
```

    greater than 50
    done



```python
favourite_numbers = [1, 2, 4, 7]
odds = [1, 3, 5, 7]

for number in favourite_numbers:
    if number in odds:
        print(number)
```

    1
    7



```python
favourite_numbers = [1, 2, 4, 7]
odds = [1, 3, 5, 7]
favourite_odds = []

for number in favourite_numbers:
    if number in odds:
        favourite_odds.append(number)

print(favourite_odds)
```

    [1, 7]


## Putting it all together

In genetics we might want to find out the reverse complement of a DNA sequence. Using what we now know, we can do it too.


```python
# reverse complement
rev_comp = ""
sequence = "ACCCTG"

#  start with reverse then add in complement

for base in sequence:
    if base == "A":
        new_base = "T"
    elif base == "T":
        new_base = "A"
    elif base == "C":
        new_base = "G"
    elif base == "G":
        new_base = "C"
    else:
        print("Unrecognised base!")
    rev_comp = new_base + rev_comp

print("The reverse complement is:", rev_comp)
```

    The reverse complement is: CAGGGT

