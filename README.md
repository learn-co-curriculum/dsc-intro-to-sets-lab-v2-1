
# Introduction to Sets - Lab

## Introduction

Probability theory is all around. A common example is in the game of poker or related card games, where players try to calculate the probability of winning a round given the cards they have in their hands. Also, in a business context, probabilities play an important role. Operating in a volatile economy, companies need to take uncertainty into account and this is exactly where probability theory plays a role.

As mentioned in the lesson before, a good understanding of probability starts with understanding of sets and set operations. That's exactly what you'll learn in this lab!

## Objectives

You will be able to:

* Use Python to perform set operations


## Exploring Set Operations Using Python

Let's consider the following sets:

   - $\Omega$ = positive integers between [1, 12]
   - $A$= even numbers between [1, 10]
   - $B = \{3,8,11,12\}$
   - $C = \{2,3,6,8,9,11\}$

#### Create sets A, B and C and the universal set $\Omega$ in Python.

Hint: For a guide to the syntax, follow some of the documentation [here](https://www.w3schools.com/python/python_sets.asp)


```python
# Create set A
A = None
print('Type A: {}, A: {}'.format(type(A), A)) # "Type A: <class 'set'>, A: {2, 4, 6, 8, 10}"
```


```python
# Create set B
B = None
print('Type B: {}, B: {}'.format(type(B), B)) # "Type B: <class 'set'>, B: {8, 11, 3, 12}"
```


```python
# Create set C
C = None
print('Type C: {}, C: {}'.format(type(C), C)) # "Type C: <class 'set'>, C: {2, 3, 6, 8, 9, 11}"
```


```python
# Create the universal set. Instead of naming it Omega, we name it U, for universal. 
U = None
print('Type U: {}, U: {}'.format(type(U), U)) # "Type U: <class 'set'>, U: {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12}"
```

Here is a table with common set operations in Python: 

| Method        |	Equivalent |	Result |
| ------                    | ------       | ------    |
| s.issubset(t)             |	s <= t     | test whether every element in s is in t
| s.issuperset(t)           |	s >= t     | test whether every element in t is in s
| s.union(t)                |	s $\mid$ t | new set with elements from both s and t
| s.intersection(t)         |	s & t      | new set with elements common to s and t
| s.difference(t)           |	s - t 	   | new set with elements in s but not in t
| s.symmetric_difference(t) |	s ^ t      | new set with elements in either s or t but not both

Use this table to compute the following:

* $ A \cap B$
* $ A \cup C$
* $A^c$
* The absolute complement of B
* $(A \cup B)^c$
* $B \cap C'$
* $A\backslash B$
* $C \backslash (B \backslash A)$
* $(C \cap A) \cup (C \backslash B)$

#### 1. $ A \cap B$


```python
A_inters_B =  None
A_inters_B # {8}
```

#### 2. $ A \cup C $


```python
A_union_C = None
A_union_C # {2, 3, 4, 6, 8, 9, 10, 11}
```

#### 3.  $A^c$ (you'll have to be a little creative here!)


```python
A_comp = None
A_comp # {1, 3, 5, 7, 9, 11, 12}
```

#### 4.  $(A \cup B)^c $


```python
A_union_B_comp = None
A_union_B_comp # {1, 5, 7, 9}
```

#### 5. $B \cap C' $


```python
B_inters_C_comp = None
B_inters_C_comp # {12}
```

#### 6. $A\backslash B$


```python
compl_of_B = None
compl_of_B # {2, 4, 6, 10}
```

#### 7. $C \backslash (B \backslash A) $


```python
C_compl_B_compl_A = None
C_compl_B_compl_A # {2, 6, 8, 9}
```

#### 8.  $(C \cap A) \cup (C \backslash B)$


```python
C_inters_A_union_C_min_B= None
C_inters_A_union_C_min_B # {2, 6, 8, 9}
```

## More Set Operations in Python

Mary is preparing for a road trip from her hometown, Boston, to Chicago. She has quite a few pets, yet luckily, so do her friends. They try to make sure that they take care of each other's pets while someone is away on a trip. A month ago, each respective person's pet collection was given by the following three sets:


```python
Nina = set(["Cat","Dog","Rabbit","Donkey","Parrot", "Goldfish"])
Mary = set(["Dog","Chinchilla","Horse", "Chicken"])
Eve = set(["Rabbit", "Turtle", "Goldfish"])
```

In this exercise, you'll be able to use the following operations:

|Operation                          |	Equivalent |	Result|
| ------                            | ------       | ------   |
|s.update(t)                        | 	$s \mid t$ 	   |return set s with elements added from t|
|s.intersection_update(t)           | 	s &= t     |	return set s keeping only elements also found in t|
|s.difference_update(t)             |	s -= t 	   |return set s after removing elements found in t|
|s.symmetric_difference_update(t)   |	s ^= t 	   |return set s with elements from s or t but not both|
|s.add(x)                           |	           |	add element x to set s|
|s.remove(x)                        |	           |	remove x from set s|
|s.discard(x)                       |	           |	removes x from set s if present|
|s.pop()                            | 	           |	remove and return an arbitrary element from s|
|s.clear()            	            |  	           |remove all elements from set s|

Sadly, Eve's turtle passed away last week. Let's update her pet list accordingly.


```python
None
Eve # should be {'Rabbit', 'Goldfish'}
```

This time around, Nina promised to take care of Mary's pets while she's away. But she also wants to make sure her pets are well taken care of. As Nina is already spending a considerable amount of time taking care of her own pets, adding a few more won't make that much of a difference. Nina does want to update her list while Marie is away. 


```python
None
Nina # {'Chicken', 'Horse', 'Chinchilla', 'Parrot', 'Rabbit', 'Donkey', 'Dog', 'Cat', 'Goldfish'}
```

Mary, on the other hand, wants to clear her list altogether while away:


```python
None
Mary  # set()
```

Look at how many species Nina is taking care of right now.


```python
None
n_species_Nina # 9
```

Taking care of this many pets is weighing heavily on Nina. She remembered Eve had a smaller collection of pets lately, and that's why she asks Eve to take care of the common species. This way, the extra pets are not a huge effort on Eve's behalf. Let's update Nina's pet collection.


```python
None
Nina # 7
```

Taking care of 7 species is something Nina feels comfortable doing!

## Optional Exercise: European Countries

Use set operations to determine which European countries are not in the European Union. You just might have to clean the data first with pandas.


```python
import pandas as pd

#Load Europe and EU
europe = pd.read_excel('Europe_and_EU.xlsx', sheet_name = 'Europe') 
eu = pd.read_excel('Europe_and_EU.xlsx', sheet_name = 'EU')

#Use pandas to remove any whitespace from names
```


```python
europe.head(3) #preview dataframe
eu.head(3)
```


```python
# Your code comes here
```

## Summary

In this lab, you practiced your knowledge on sets, such as common set operations and how to use sets in Python! 
