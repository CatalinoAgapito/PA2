# PA#2
### Name: AGAPITO, Catalino D.R.
### Section: 2ECE-C
### Date Submitted: September 3, 2026

In this Program Assignment, three different problems were asked to demonstrate proficiency in NumPy array operations. Each problem focuses on different aspects of numerical computing with NumPy, from array creation and manipulation to statistical computations and Boolean filtering.

# Problem 1: Reproducible Normalization 

In this problem, it requires creating a reproducible 5x5 array of random integers and normalizing it using the z-score formula. The goal is to demonstrate understanding of random number generation, array statistics, and vectorized operations



```
import numpy as np

np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))

X_normalized = (X - X.mean()) / X.std()

#Required CHecks
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


In order to create a reproducible random array and normalize it, the program first sets a random seed to ensure the same numbers are generated every time. A 5×5 array of random integers between 10 and 100 is then created using NumPy's randint function. The normalization is performed by subtracting the mean of all elements and dividing by the standard deviation, resulting in a normalized array with mean 0 and standard deviation 1. The program displays the original array, normalized array, and verifies the mean and standard deviation.



# Problem 2: Cubes Divisible by 4
In this problem, you are asked to create a 10×10 array of cubes of the first 100 positive integers, then select only those cubes divisible by 4. This demonstrates array creation, reshaping, and Boolean filtering.


````
C = np.arange(1, 101) ** 3
C = C.reshape(10, 10)

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
In order to create the array and filter values divisible by 4, the program first generates numbers 1 to 100 and cubes each element using vectorized exponentiation. The resulting 1D array is reshaped into a 10×10 matrix, preserving row-major order. Boolean filtering is then applied to select only elements where the cube is divisible by 4, using the modulo operator to create a mask. The program displays the shape of the array, the filtered values, and the count of selected elements.


# Problem 3: Above-Mean Squares 
In this problem, you are asked to create a 6×6 array of squares of the first 36 positive integers, compute the mean, and select elements greater than the mean. This demonstrates array creation, statistical computation, and conditional selection.


````
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
````


In order to create the squares array and filter values above the mean, the program first generates numbers 1 to 36 and squares each element using vectorized exponentiation. The resulting 1D array is reshaped into a 6×6 matrix, preserving row-major order. The mean of all elements is computed using NumPy's mean function. Boolean filtering is then applied to select only elements greater than the computed mean. The program displays the original array, the mean value, the filtered values, and the count of selected elements.
