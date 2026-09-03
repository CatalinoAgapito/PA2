# PA#2
### Name: AGAPITO, Catalino D.R.
### Section: 2ECE-C
### Date Submitted: September 3, 2026

In this Program Assignment, three different problems were asked to demonstrate proficiency in NumPy array operations. Each problem focuses on different aspects of numerical computing with NumPy, from array creation and manipulation to statistical computations and Boolean filtering.

# Problem 1:REPRODUCIBLE NORMALIZATION PROBLEM

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
In order to create a reproducible random array and normalize it, the program first sets a random seed to ensure the same numbers are generated every time. A 5x5 array of random

# Problem 2: CUBES DIVISIBLE BY 4 PROBLEM





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


# Problem 3: ABOVE-MEAN SQUARES PROBLEM






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
