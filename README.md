# Math_for_Data_Science

Math project for Data Science
Group Members:
Nikita Chistyakov
Ranjitha Valdivel
Loic Steve Fohoue Chendjou

There are two projects in the repository; one related to the diagonalization of matrices using python
And the second one is the PCA(Principle Component Analysis

Topic 1: 
Diagonalization of matrix

Objective: 
We set out to prove matrix diagonalization (non-defective) by first defining a matrix and then calculating its eigenvalues and eigenvectors. This was interesting to us since the eigenvectors are used in the original PageRank algorithm that allowed Google to create the world’s best search engine.

Our process: 
To find out if a matrix is diagonalizable; the first step is to check whether this matrix is a square matrix, defined by a matrix of n*n. 
Using Python in a jupyter notebook we are setting a condition: if matrix.shape[0] != matrix.shape[1]. 
The matrix is not a square if it returns false; otherwise, it is a square matrix, and then when the matrix respects this condition, we move to the second step and have to find the eigenvalues.

Determining the characteristic polynom by subtracting X from the value situated in the diagonal and then computing the determinant of this new matrix obtained by subtraction of the X to the value situated in the diagonal. 
However in Python there are libraries called numpy and Scipy that handle these characteristics, so after computing the determinant of this new matrix, we solve the linear equation, and obtain it by computing the determinant meaning det(M-IX)=0.

Next step is to find eigenvectors based on the eigenvalues we found from the equation mentioned above. There are also the same previous libraries used to do so, but to do so we take each eigenvalue and then, we find the kernel of the MX-valiX, validating for each eigenvalue.

Next step after doing that based on the vectors found, we can easily check whether the matrix A is diagonalizable; meaning if the number of eigenvectors is equal to the dimension of the matrix we conclude that the matrix is diagonalizable. If the number of eigenvectors is less than the dimension of the matrix, we conclude that the matrix is not diagonalizable.

Now in case the

Define matrix:



Check if A is a square matrix:




Find eigenvalues and eigenvectors:
Eigenvalues: L1, L2, ... Ln 
Eigenvectors: U1, U2, .......Un
Check if the number of eigenvectors is equal to the dimension of the number of columns and rows. Check if there are enough linearly independent eigenvectors.



IV. Form diagonalized matrix:

 	D = 
L1 
0
0
0
L2
0
0
0
L3




V. Calculate PDP-1:
We do that by inverting P to obtain P-1

VI. Calculate diagonalized matrix:


VII. Verify that matrices match:

VIII. Final check of a random matrix:




