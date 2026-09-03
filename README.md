# PA#2
## Name: Nissi ALeichem B. Sulit
## Section: 2ECE-B
## Date Submitted: September 3, 2026

In this Program Assignment, there are three tasks to demonstrate the use of NumPy array operations. Each problem highlights a specific application of numerical computing in Numpy, including generating and modifying arrays, perfoming statistical calculations, and using Boolean conditions to filter data.

#Problem 1: Reproducible Normalization

This problem involves generating a reproducible 5×5 array containing random integers and applying z-score normalization to its elements. The main objective is to demonstrate the use of random number generation, statistical functions, and vectorized array operations in NumPy.

To generate the same random array each time the program runs, a fixed random seed is first assigned. The program then creates a 5×5 array containing random integers ranging from 10 to 100 using NumPy's randint() function. Z-score normalization is performed by subtracting the overall mean from each element and dividing the result by the standard deviation. This produces a normalized array with a mean close to 0 and a standard deviation of 1. Finally, the program prints the original array, the normalized values, and the calculated mean and standard deviation to verify the results.

```python
import numpy as np
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))

X_normalized = (X - X.mean()) / X.std()

#Required 
print("X:")
print(X)

print("\nX_normalized:")
print(X_normalized)

print("\nMean of X_normalized:")
print(X_normalized.mean())

print("\nStandard deviation of X_normalized:")
print(X_normalized.std())

np.save("X_normalized.npy", X_normalized)

````

#Problem 2: Cubes Divisible by 4 

This problem involves creating a 10×10 array containing the cubes of the first 100 positive integers and selecting the cubes divisible by 4. The numbers from 1 to 100 are cubed using vectorized operations and reshaped into a 10×10 array. Boolean filtering with the modulo operator is then used to find the values divisible by 4. The program displays the array shape, selected values, and their total count.

```python
C = np.arange(1,101)**3
C = C.reshape(10,10)

div_by_4 = C[C % 4 == 0]

#Required Checks
print("Shape of C:")
print(C.shape)

print("\nValues divisible by 4:")
print(div_by_4)

print("\nNumber of selected elements:")
print(div_by_4.size)

np.save("div_by_4.npy", div_by_4)
````

#Problem 3: Above-Mean Squares

This problem requires creating a 6×6 array containing the squares of the first 36 positive integers and selecting values greater than the mean. The numbers from 1 to 36 are squared and reshaped into a 6×6 array. The mean is calculated using NumPy's mean() function, followed by Boolean filtering to identify values above the mean. The program displays the array, mean, selected values, and their count.

```python
S = np.arange(1, 37) ** 2
S = S.reshape(6, 6)

S_mean = S.mean()

above_mean = S[S > S_mean]

#Required Checks
print("S:")
print(S)

print("\nMean of S:")
print(S_mean)

print("\nValues above the mean:")
print(above_mean)

print("\nNumber of selected elements:")
print(above_mean.size)

np.save("above_mean.npy", above_mean)
```
