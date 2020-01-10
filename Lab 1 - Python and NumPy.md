---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.1'
      jupytext_version: 1.2.4
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Name(s)
**Ethan Moore and Ajay Patel**


**Instructions:** This is an individual assignment, but you may discuss your code with your neighbors.


# Python and NumPy

While other IDEs exist for Python development and for data science related activities, one of the most popular environments is Jupyter Notebooks.

This lab is not intended to teach you everything you will use in this course. Instead, it is designed to give you exposure to some critical components from NumPy that we will rely upon routinely.

## Exercise 0
Please read and reference the following as your progress through this course. 

* [What is the Jupyter Notebook?](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb#)
* [Notebook Tutorial](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook)
* [Notebook Basics](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb)

**In the space provided below, what are three things that still remain unclear or need further explanation?**


1. Is there a shortcut to immediately add or delete cells?

2. Is there an easy way to convert work done in a .ipynb file to a .py file?

3. What are containers to run software? And do we need them in this course?


## Exercises 1-7
For the following exercises please read the Python appendix in the Marsland textbook and answer problems A.1-A.7 in the space provided below.


## Exercise 1

```python
# YOUR SOLUTION HERE
#a=1000
# print('this is my answer',a+1) 
import numpy as np

a = np.array([[2,2,2,2]] * 6)
a
```

## Exercise 2

```python
# YOUR SOLUTION HERE\
c = np.array([[1,1,1,1]] * 6)
d = np.eye(6,4)

b = d + d + c
b
```

## Exercise 3

```python
# YOUR SOLUTION HERE

a * b

#This is the code below to answer part 2
# np.dot(a,b)
```

a * b works because the dimensions of the two matrices are the same. 

np.dot(a,b) does not work because the number of columns in the matrix a is not the same as the number of rows in matrix b


## Exercise 4

```python
# YOUR SOLUTION HERE

print(np.dot(a.transpose(), b))
print("")
print(np.dot(a, b.transpose()))
```

The results are different shapes because the first matrix multiplication is fit to be made a product that is a 4x4 matrix and the second matrix result is a 6x6 for the same reason


## Exercise 5

```python
# YOUR SOLUTION HERE
print("Hello World")
```

## Exercise 6

```python
# YOUR SOLUTION HERE

arr = np.random.randint(0,100,10)
print("mean:", arr.mean())
print("standard deviation:", arr.std())
print("max:", arr.max())
print("min:", arr.min())
print("sum:", arr.sum())

```

## Exercise 7

```python
# YOUR SOLUTION HERE

def count_1s(arr):
    count  = 0
    for i in range(len(arr)):
        if arr[i] == 1:
            count += 1 
    print(count)

print(arr)
print("Number of 1s:")
count_1s(arr)

print(np.where(arr == 1, 1, 0).sum())
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
# YOUR SOLUTION HERE
import pandas as pd

a = pd.DataFrame({
    "A" : pd.Series(2, index=list(range(6))),
    "B" : pd.Series(2, index=list(range(6))),
    "C" : pd.Series(2, index=list(range(6))),
    "D" : pd.Series(2, index=list(range(6)))
})

print(a)
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
# YOUR SOLUTION HERE

b = pd.DataFrame({
    "A" : np.array([3, 1, 1, 1, 1, 1]),
    "B" : np.array([1, 3, 1, 1, 1, 1]),
    "C" : np.array([1, 1, 3, 1, 1, 1]),
    "D" : np.array([1, 1, 1, 3, 1, 1])
})

print(b)
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
# YOUR SOLUTION HERE

print(a * b)

# This is the code below to answer part 2
# print(a.dot(b))
```

a * b works because the product is the result of the same position in each dataframe being multiplied together.

a.dot(b) does not work because dataframe a does not have the same number of columns as the number of rows in dataframe b.


## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
# YOUR SOLUTION HERE


def count_1s(df):
    count  = 0
    for i in range(len(df)):
        if arr[i] == 1:
            count += 1 
    print(count)

print(a)
print("")
print("Number of 1's: ")
count_1s(a)

print("")
print(np.where(a == 1, 1, 0).sum())
```

## Exercises 12-14
Now let's look at a real dataset, and talk about ``.loc``. For this exercise, we will use the popular Titanic dataset from Kaggle. Here is some sample code to read it into a dataframe.

```python
titanic_df = pd.read_csv(
    "https://raw.githubusercontent.com/dlsun/data-science-book/master/data/titanic.csv"
)
titanic_df
```

Notice how we have nice headers and mixed datatypes? That is one of the reasons we might use Pandas. Please refresh your memory by looking at the 10 minutes to Pandas again, but then answer the following.


## Exercise 12
How do you select the ``name`` column without using .iloc?

```python
## YOUR SOLUTION HERE

titanic_df[["name"]].head()
```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
## YOUR SOLUTION HERE
titanic_df.set_index('sex',inplace=True)
```

```python
titanic_df.loc["female"].head()
```

```python
print(len(titanic_df.loc["female"]))
```

## Exercise 14
How do you reset the index?

```python
## YOUR SOLUTION HERE
titanic_df.reset_index().head()
```

```python

```
