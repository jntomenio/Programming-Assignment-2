[![Up to Date](https://github.com/ikatyang/emoji-cheat-sheet/workflows/Up%20to%20Date/badge.svg)](https://github.com/ikatyang/emoji-cheat-sheet/actions?query=workflow%3A%22Up+to+Date%22)

<!-- ![Build Status](https://travis-ci.org/yourusername/yourproject.svg?branch=main) -->

# :bookmark_tabs: PA2 - Numerical Python


> [!NOTE]
> :open_book: *NumPy (Numerical Python)* - is an open-source Library widely used in science and engineering. The NumPy Library contains multidimensional array data structures, such as the homogeneous, N-dimensional ndarray, and an extensive Library of functions that are known for their efficiency in operating on these data structures.[^1] This repository incorporates Python code to decipher two programming problems titled: **Normalization** and **Divisible By 3**.

[^1]: https://numpy.org/doc/stable/user/absolute_beginners.html

---

## 1. *Normalization Problem*
Normalization is one of the most basic preprocessing techniques in data analytics. This involves centering and scaling process. Centering means subtracting the data from the mean and scaling means dividing with its standard deviation. Mathematically, normalization can be expressed as:

![image](https://github.com/user-attachments/assets/4d721c9d-034e-4c27-be01-c81fce3817fc)

> [!IMPORTANT]
> In Python, element-wise mean and element-wise standard deviation can be obtained by using *.mean()* and *.std()*.

 ### EXAMPLE
- In this problem, generate randomize 5 x 5 ndarray and store it to variable X. Then, Normalize X.
- :floppy_disk: Save your normalized ndarray as `X_normalized.npy`

##### :keyboard: *Input:*
A randomly generated 5x5 ndarray.
```python
import numpy as np

# Generate a 5x5 matrix of random numbers between 0 and 1
X = np.random.random((5, 5))

def normalization(X):
 # Normalize the input matrix X by subtracting the mean and dividing by the standard deviation
    normal = (X - np.mean(X)) / np.std(X)
    return normal

# Save the normalized matrix to a .npy file
np.save('X_normalized.npy', normalization(X))
# Display the original randomize matrix
X
```

##### :heavy_check_mark: *One of the Expected Input (random numbers):*
![image](https://github.com/user-attachments/assets/1652f345-53ef-4b99-a935-a0fb214d6420)

##### :computer: *Output:*
A normalized 5x5 ndarray saved in *X_normalized.npy*
```python
# Load the normalized matrix from a .npy file
norm_matrix = np.load("X_normalized.npy")

# Calculate the standard deviation of the original matrix X and round it to 4 decimal places
rounded_std = round(np.std(X), 4)

# Print the mean of the original matrix X, the rounded standard deviation, and the normalized matrix
print("The Mean for overall matrix:", np.mean((X)), 
      "\n\nThe Standard Deviation of the matrix:", rounded_std, 
      "\n\nAs a result the normalized matrix:\n\n", norm_matrix)
```

##### :white_check_mark: *Expected Output:*
![image](https://github.com/user-attachments/assets/8c937782-faae-4f02-9970-43a24a7a8cc5)

--- 

## 2. *Divisible By 3 Problem*
### EXAMPLE
- Create a 10 x 10 array which are the squares of the first 100 positive integers
- From this array, determine all the elements that are divisible only by 3.

#### :keyboard: *Input:*
```python
import numpy as np

# Create an array of squares of the first 100 positive integers
A = np.arange(1,101,1)**2

# Reshape the array into a 10x10 matrix
A = A.reshape(10,10)

def div3(array):
    # Filter the array to include only elements that are divisible by 3
    array = array[array%3 == 0]
    return array

# Save the filtered array (elements divisible by 3) to a .npy file
np.save("div_by_3.npy",div3(A))

# Display the 10x10 matrix of squares
print("The Squares of the First 100 Positive Integers:\n\n",A)
```

##### :heavy_check_mark: *Expected Input:*
![image](https://github.com/user-attachments/assets/17475aad-2730-4f68-80a8-73adadc1ac83)

##### :computer: *Output:*
```python
# Load the NumPy array from the specified file "div_by_3.npy"
div3_matrix = np.load("div_by_3.npy")

# Print the elements that are divisible by 3 using the contents of the div3_matrix
print("The Elements that are divisible by 3:\n\n", div3_matrix)
```
##### :white_check_mark: *Expected Output:*
![image](https://github.com/user-attachments/assets/0a24e9cc-b0dd-4fff-91ab-2a616806efa0)
