## **EXPERIMENT #2 - Numerical Python**
### Name: Tomenio, Julian Bernice Kristoffer
### Section: 2ECE-A

#### Date Submitted: September 03, 2024

## NORMALIZATION PROBLEM
Normalization is one of the most basic preprocessing techniques in data analytics. This involves centering and scaling process. Centering means subtracting the data from the mean and scaling means dividing with its standard deviation. Mathematically, normalization can be expressed as:

                                                   ![image](https://github.com/user-attachments/assets/4d721c9d-034e-4c27-be01-c81fce3817fc)

In Python, element-wise mean and element-wise standard deviation can be obtained by using .mean() and
.std() calls.
In this problem, create a random 5 x 5 ndarray and store it to variable X. Normalize X. Save your normalized
ndarray as X_normalized.npy

```python
import numpy as np

X = np.random.random((5, 5))

def normalization(X):
	normal = (X - np.mean(X))/np.std(X)
	return normal

np.save('X_normalized.npy', normalization(X))
X

norm_matrix = np.load("X_normalized.npy")
rounded_std = round(np.std(X),4)

print("The Mean for overall matrix:",np.mean((X)),"\n\nThe Standard Deviation of the matrix:",rounded_std,"\n\nAs a result the normalized matrix:\n\n",norm_matrix)
```

## DIVISIBLE BY 3 PROBLEM
```python
import numpy as np

A = np.arange(1,101,1)**2

A = A.reshape(10,10)

def div3(array):
	array = array[array%3 == 0]
	return array

np.save("div_by_3.npy",div3(A))

print("The Squares of the First 100 Positive Integers:\n\n",A)

div3_matrix = np.load("div_by_3.npy")

print("The Elements that are divisible by 3:\n\n",div3_matrix)
```
