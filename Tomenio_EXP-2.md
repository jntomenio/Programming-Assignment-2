## **EXPERIMENT #2 - Numerical Python**
### Name: Tomenio, Julian Bernice Kristoffer
### Section: 2ECE-A

#### Date Submitted: September 03, 2024

## NORMALIZATION PROBLEM
import numpy as np


def alphabet_soup (word):
    #Sort the characters and join them into a single string
    return ''.join(sorted(word))

#Ask the user for input
user_word = input("Enter a word: ")

#Get and print the alphabetically sorted word
print(alphabet_soup(user_word))


X = np.random.random((5, 5))

def normalization(X):
	normal = (X - np.mean(X))/np.std(X)
	return normal

np.save('X_normalized.npy', normalization(X))
X

norm_matrix = np.load("X_normalized.npy")
rounded_std = round(np.std(X),4)

print("The Mean for overall matrix:",np.mean((X)),"\n\nThe Standard Deviation of the matrix:",rounded_std,"\n\nAs a result the normalized matrix:\n\n",norm_matrix)

## DIVISIBLE BY 3 PROBLEM
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
