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





Topic 2: 
Principle Component Analysis (PCA)

Objective:
We were interested in exploring this widely used technique that helps to identify patterns in the data by reducing its dimensionality. This concept integrates both machine learning and data analysis. As a method that simplifies the complexity of the data, it transforms long features into a lower dimensional space while retaining most of the information. In other words, it can be explained by a metaphor: summarizing a long book in several pages while keeping the most relevant points.

PCA is especially useful when dealing with high-dimensional datasets where the number of features is large. It can be used for various applications such as image processing, speech recognition, and data compression.

Our process: 
The aim of our second project is to perform a PCA in Python using the scikit-learn library; but we have two phases:
First, by using a sample dataset from scikit-learn to see how it works
And second, by using a data set downloaded from the Kaggle.com website and we use it to perform the second part of our project






Import libraries and load data:
We are coming across and using the scikit-learn for the first time
We have decided on analysing a house-prices dataset from Kaggle


Standardize data:
PCA is sensitive to the scale of the input data, so it’s important to standardize the data before performing PCA. 
Data must be in numerical format.
Standardization involves scaling the data so that it has a mean of 0 and a standard deviation of 1.




Compute covariance matrix:
The next step is to compute the covariance matrix of the standardized data. 
The covariance matrix represents the relationships between the different features in the data.



Compute eigenvectors and eigenvalues of the covariance matrix:
The eigenvectors and eigenvalues of the covariance matrix are used to determine the principal components of the data. 
The eigenvectors represent the directions of maximum variance in the data, while the corresponding eigenvalues represent the amount of variance explained by each eigenvector.





V. 	Sorting eigenvalues in descending order:
We can then select the primary components that account for the most variance in the data. We sort in from highest to lowest so that we can take the highest value for the next step.




VI. 	Chosing the principal component:
To accomplish this, we can choose the top k eigenvectors, which are those that match the k biggest eigenvalues.
For example, we'll choose k=2 and choose the first two eigenvectors in the sorted eigenvectors list to serve as our primary components.



VII. 	Project data onto a lower-dimensional linear subspace: 
In the final step of this stage, the data must be projected onto the principal components-defined lower-dimensional linear subspace.
This will transform the data from its original high-dimensional space into a lower-dimensional space while retaining as much of the original information as possible.




VIII. 	Create a PCA object with 2 components:
This code performs Principal Component Analysis (PCA) on a dataset y and reduces its dimensionality to 2 components using the PCA class from the “sklearn.decomposition” module.
Once the code is executed, the PCA object will contain the learned PCA model, which can be used to transform new data into lower-dimensional space. The “y_reduced” variable will contain the transformed dataset with only 2 dimensions, which can be used for further analysis or visualization.




IX. 	We can then plot the reduced data using matplotlib:
This code visualizes the results of the PCA by creating a scatter plot of the transformed dataset y_reduced in two dimensions, where the x-axis represents the first principal component and the y-axis represents the second principal component.
Once the code is executed, a scatter plot will be displayed on the screen showing the transformed dataset y_reduced in two dimensions. This plot can be used to gain insights into the structure of the data and to identify patterns or clusters of observations.



X. 	Evaluating the results of PCA:
In order to be sure that Principal Component Analysis (PCA) served its intended function, it is crucial to assess the outcomes.
Variance explained, cumulative variance explained, and scree plot are just a few from a list of methods for assessing the outcomes of PCA.

After performing Principal Component Analysis (PCA), it is important to evaluate the results to ensure that it has achieved its purpose. There are several ways to evaluate the results of PCA, including variance explained, cumulative variance explained, and scree plot.

XI. 	Fit corresponding variances:
This method in scikit-learn fits the PCA model to the data

		

XII. 	Calculated-variance explained:
In this code, we are calculating the variance explained by each principal component. The PCA object that we created earlier using sklearn.decomposition module has a built-in method called explained_variance_ratio_ which returns an array of the variance explained by each principal component.



XIII. 	Calculated cumulative-variance explained:
This is a 1D array or a list of the explained variance ratios of each of the principal components.
The result represents the proportion of the total variance in the original data that can be attributed to that component.



XIV.	Lastly, a Scree Plot:
The Scree plot is a graphical representation of the amount of variance explained by each principal component in a Principal Component Analysis (PCA). The plot displays the eigenvalues of each principal component in descending order on the x-axis and the percentage of variance explained by each principal component on the y-axis.
Also used to determine the number of principal components to retain in a dataset. Typically, the eigenvalues decrease rapidly for the first few principal components and then level off. The number of principal components to retain is determined by the "elbow" point in the Scree plot, which represents the point where the eigenvalues start to level off.



















References:
https://pieriantraining.com/machine-learning-in-python-principal-component-analysis-pca/
https://towardsdatascience.com/principal-component-analysis-pca-explained-visually-with-zero-math-1cbf392b9e7d
https://www.jcchouinard.com/pca-with-python/


