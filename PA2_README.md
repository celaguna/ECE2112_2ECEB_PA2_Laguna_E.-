# Programming Assignment 2

**Student Name:** Laguna, Carlvinz E.  
**Section:** 2ECE-B  
**Course Code:** ECE2112  

---

## Intended Learning Outcomes
1. To identify the codes and functions incorporated in the Numpy library.
2. To be able to apply and use the different codes and functions in creating a Python program using a
   Numpy library.

---

## What to Expect
This README documents two Python programs:
1. Normalization Problem (data preprocessing using mean and standard deviation)
2. Divisible by 3 Problem (array creation, reshaping, and boolean indexing) 

Each section includes the **actual code with line-by-line explanations inside the code comments**, describing the process and why each 
function or operation is used.

---

## Table of Contents
1. [Intended Learning Outcomes](#intended-learning-outcomes)  
2. [What to Expect](#what-to-expect)  
3. [Normalization Problem](#normalization-problem)  
4. [Divisible by 3 Problem](#divisible-by-3-problem)  
5. [Conclusion](#-conclusion)
6. [Programming Assingment 2 .ipynb file](PA2_LAGUNA.ipynb)

---

## Normalization Problem
### Problem Description
The goal of this problem is to create a random 5x5 matrix and normalize its values using the formula:

𝑍 = 𝑋 − 𝑥̅ / 𝜎 where 𝑥̅ is the mean and 𝜎 is the standard deviation.

This introduces the concept of data preprocessing and the use of NumPy’s mathematical functions like .mean() and .std() to standardize datasets.

### Code

```python
# Import numpy library as np
import numpy as np

# Create a random 5x5 ndarray with values between 0 and 1
X = np.random.rand(5, 5)

# Compute the mean of the array
mean_X = X.mean()

# Compute the standard deviation of the array
std_X = X.std()

# Normalize the array using the formula (X - mean) / std
X_normalized = (X - mean_X) / std_X

# Save the normalized array into a file named 'X_normalized.npy'
np.save("X_normalized.npy", X_normalized)

# Display the original 5x5 matrix
print("Original X:\n", X)

# Display the normalized 5x5 matrix
print("\nNormalized X:\n", X_normalized)
```

**Step 1: Import NumPy Library**
- We import the NumPy library and give it the alias np.
- NumPy provides tools for arrays, random numbers, and mathematical functions.
- Using np makes it shorter and easier to call functions.

```python
import numpy as np
```
**Step 2: Create a Random 5x5 Array**
- np.random.rand(5, 5) generates a 5x5 matrix filled with random numbers between 0 and 1.
- This will serve as our dataset for normalization.

```python
X = np.random.rand(5, 5)
```
**Step 3: Compute the Mean of the Array**
- X.mean() calculates the average value of all 25 numbers in the matrix.
- The mean will be used in the normalization formula.

```python
mean_X = X.mean()
```
**Step 4: Compute the Standard Deviation of the Array**
- X.std() calculates how spread out the numbers are from the mean.
- The standard deviation is needed to scale the values during normalization.

```python
std_X = X.std()
```
**Step 5: Normalize the Array**

Apply the formula:

𝑍 = 𝑋 − 𝑥̅ / 𝜎

where 𝑥̅ is the mean and 𝜎 is the standard deviation.

- This process shifts the mean of the data to 0 and the standard deviation to 1.

```python
X_normalized = (X - mean_X) / std_X
```
**Step 6: Save the Normalized Array**
- np.save("X_normalized.npy", X_normalized) saves the normalized matrix into a file.
- The .npy format is NumPy’s binary file type for storing arrays.

```python
np.save("X_normalized.npy", X_normalized)
```
**Step 7: Display the Original Array**
- Print the original 5x5 random matrix to compare with the normalized one.

```python
print("Original X:\n", X)
```
**Step 8: Display the Normalized Array**
- Print the normalized 5x5 matrix.
- The new values should have a mean close to 0 and a standard deviation of 1.

```python
print("\nNormalized X:\n", X_normalized)
```

## Takeaways
1. import numpy as np is used to access NumPy functions easily with the alias np.
2. np.random.rand() generates a matrix of random numbers between 0 and 1.
3. .mean() computes the average of all elements in an array.
4. .std() calculates the spread of data (standard deviation).
5. Normalization uses the formula (X - mean) / std to center data around 0 with a standard deviation of 1.
6. np.save() stores the result in a .npy file for later use.
7. print() is used to display both the original and the normalized arrays.

---

## Divisible by 3 Problem
### Problem Description
The goal of this problem is to generate a 10x10 matrix containing the squares of the first 100 positive integers and then filter out all elements that are divisible by 3.
This introduces the concept of NumPy array manipulation, including array generation (np.arange()), reshaping (.reshape()), and boolean indexing for filtering data.

### Code

```python
# Import numpy library as np
import numpy as np

# Create an array of integers from 1 to 100
numbers = np.arange(1, 101)

# Square each integer to get the squares of the first 100 positive integers
squares = numbers**2

# Reshape the 1D array of 100 squares into a 10x10 matrix
A = squares.reshape(10, 10)

# Select all elements in A that are divisible by 3
div_by_3 = A[A % 3 == 0]

# Save the elements divisible by 3 into a file named 'div_by_3.npy'
np.save("div_by_3.npy", div_by_3)

# Display the 10x10 matrix of squares
print("Matrix A (squares of first 100 positive integers):\n", A)

# Display only the elements that are divisible by 3
print("\nElements divisible by 3:\n", div_by_3)
```

**Step 1: Import NumPy Library**
- We import the NumPy library and give it the alias np.
- This allows us to use NumPy’s functions for array creation and manipulation.

```python
import numpy as np
```
**Step 2: Create an Array of Integers from 1 to 100**
- np.arange(1, 101) creates a 1D array containing numbers from 1 to 100.
- This will be the base sequence that we square later.

```python
numbers = np.arange(1, 101)
```
**Step 3: Square Each Integer**
- numbers**2 squares every value in the array.
- This gives us the squares of the first 100 positive integers.

```python
squares = numbers**2
```
**Step 4: Reshape into a 10x10 Matrix**
- .reshape(10, 10) converts the 1D array of 100 squares into a 10x10 matrix.
- This makes the data easier to visualize and structured as required by the problem.

```python
A = squares.reshape(10, 10)
```
**Step 5: Select Elements Divisible by 3**
- A % 3 == 0 creates a Boolean mask (True/False values) where numbers divisible by 3 are True.
- A[A % 3 == 0] uses this mask to extract only the elements divisible by 3.

```python
div_by_3 = A[A % 3 == 0]
```
**Step 6: Save the Result into a File**
- np.save("div_by_3.npy", div_by_3) saves the filtered elements into a .npy file.
- This allows the result to be loaded and reused later.

```python
np.save("div_by_3.npy", div_by_3)
```
**Step 7: Display the 10x10 Matrix**
- Print the full 10x10 matrix of squares so we can see the dataset before filtering.

```python
print("Matrix A (squares of first 100 positive integers):\n", A)
```
**Step 8: Display Elements Divisible by 3**
- Print only the extracted numbers that are divisible by 3.

```python
print("\nElements divisible by 3:\n", div_by_3)
```

## Takeaways
1. np.arange() generates sequences of numbers, useful for creating ranges.
2. Exponentiation (**2) can be applied directly to arrays to square all elements.
3. .reshape() changes the structure of an array without changing its values.
4. Boolean indexing (A[A % 3 == 0]) is a powerful way to filter values in NumPy arrays.
5. np.save() allows saving extracted or processed data for future use.
6. print() is used to display both the entire dataset and the filtered results.

---

# 📌 Conclusion 

In this assignment, I implemented and explained two Python problems in detail:

1. **Normalization Problem** → Demonstrated how to use NumPy’s mathematical functions (.mean(), .std()) to normalize data so it has a mean of 0 and a standard deviation of 1.
2. **Divisible by 3 Problem** → Showed the use of NumPy array creation and manipulation (np.arange(), .reshape(), boolean indexing) to generate data, reshape it, and filter elements based on divisibility.

Across both problems, a few common programming concepts were reinforced:
- NumPy arrays (ndarrays) are powerful for handling structured data efficiently.
- Built-in NumPy methods make mathematical operations and array transformations much simpler.
- Boolean indexing provides a clean way to filter data without explicit loops.
- Saving with .npy files ensures that processed data can be reused later.

Overall, these exercises taught me not just how to apply NumPy functions, but also how to document the reasoning behind each line of code, making the solutions clearer, reusable, and easier to understand.

---


































