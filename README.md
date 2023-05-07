Download Link: https://assignmentchef.com/product/solved-icsi431-homework-1
<br>
<h1>1        Data analysis</h1>

In a statistical survey of 2000 families on ownership of cars 30 families responded that they do not own a car, 470 families owned 1, 850 families owned 2, 490 families owned 3, 150 owned 4, and there were 10 families which owned 10 cars each.

<strong>(a)[5 pts] </strong>Plot the sample-based Probability Mass Function (PMF) and Cumulative Distribution Function (CDF) of the random variable corresponding to <strong>number of cars per family</strong>.

<strong>(b)[5 pts] </strong>Calculate the expected <strong>number of cars per family </strong>and its variance. Show the steps of your calculation.

<strong>(d)[5 pts] </strong>Calculate the expected value of <strong>number of cars per family </strong>if you exclude the families with 10 cars. Is the mean (as compared to part <strong>b</strong>) stable or sensitive to the removal of these data points? What other statistical measures are there to estimate the average behavior? Are they less or more stable with regards to the outliers? Justify your answer by computing those alternative measures for the original sample.

<strong>(e)[5 pts] </strong>Create a box plots for the <strong>number of cars per family </strong>for the variables <em>X<sub>all </sub></em>(cars per family including all observations) and <em>X</em><sub>−10 </sub>(cars per family after excluding the 10-car families). (don’t use python libraries for this – just draw it by hand in your submission). Look here: http://www.physics. csbsju.edu/stats/box2.html for examples of box plots. You should have two boxes one for <em>X<sub>all </sub></em>and one for <em>X</em><sub>−10 </sub>with their specific statistics: mean, median, ranges and inter-quantile ranges (see slides on numeric attributes for details).

<h1>2           Irreducible data example</h1>

In class we discussed that not all datasets’ dimensionality can be successfully reduced using PCA.

<strong>(a)[2 pts] </strong>Discuss the cases when PCA will fail.

<strong>(b)[3 pts] </strong>How do we quantify that it fails?

<strong>(c)[5 pts] </strong>Provide an example dataset of 2D points (specify the points as vectors of numbers) in which PCA will not work well for dimensionality reduction. Explain why. <em>Hint: Think of 2D points and reduction to 1D.</em>

<h1>3          Dimensionality reduction</h1>

For this question you will use the Cloud Dataset from the UCI ML repository: https://archive.ics.uci.edu/ml/datasets/Cloud. Read about it to get familiar with what is measured. Within the data, there are two datasets: DB #1 and DB #2. For this homework, just use the 1024 vectors in <em>DB #1</em>. Use python for all your programming. You will have to submit your code in LastnameFirstnameCode.zip together with the relevant write-up in the main solution file LastnameFirstnameSolution.pdf.

<strong>(a)[5 pts] </strong>Load the data into a python program and center it. Note: there should be a function called <em>center() </em>in your code that achieves this.

<strong>(b)[5 pts] </strong>Compute the covariance matrix of the data Σ. <em>Hint: by using the definition of sample covariance, as a matrix product or as a sum of outer products. See book for details. </em>Use Numpy for linear algebra computations (https://docs.scipy.org/doc/numpy-1.13.0/reference/routines.linalg.html).As a result you should have a function <em>covar() </em>in your code which does not use the built-in covariance functions.

<strong>(c)[5 pts] </strong>Compute the eigenvectors and eigenvalues of Σ. The numpy linear algebra module referenced above has a function that can help.

<strong>(d)[10 pts] </strong>Determine the number of principal components (PCs) <em>r </em>that will ensure 90% retained variance? How did you compute this? Provide a function in your code that determines <em>r </em>based on an arbitrary percentage <em>α </em>of retained variance.

<strong>(e)[10 pts] </strong>Plot the first two components in a figure with horizontal axis (x) corresponding to the dimensions and vertical axis (y) corresponding to the magnitude of the component in this dimension. There will be 2 traces with d points in this figure. Include the figure in your LastnameFirstnameSolution.pdf. Also save the top two components in a text file ”Components.txt”, with each component on a separated line and represented as <em>d </em>comma separated numbers (i.e. the file should have two lines with <em>d </em>numbers separated by commas). Include ”Components.txt” in your LastnameFirstnameCode.zip.

<strong>(f)[10 pts] </strong>Compute the reduced dimension data matrix <em>A </em>with two dimensions by projection on the first two PCs. Plot the points using a scatter plot (two dimensional diagram that places each sample <em>i </em>according to its new dimensions <em>a<sub>i</sub></em><sub>1</sub><em>,a<sub>i</sub></em><sub>2</sub>). Discuss the observations. Are there clusters of close-by points? What is the retained variance for <em>r </em>= 2? Argue for or against whether these are sufficient dimensions.

<strong>(g)[5 pts] </strong>Study the PCA implementation in pythons’ sklearn library https:// scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA. html#sklearn.decomposition.PCA. Do PCA using the library on the same data. Do the eigenvalues approximately match to what you computed above?

<h1>4           Kernel methods</h1>

Consider the problem of finding <em>the most dissimilar diametric pair (MDDP)</em>: this is a pair of data points that are dissimilar from the mean and also dissimilar from each other. Below is an algorithm that would find such a pair given a data matrix <em>D</em>:

<strong>Result: </strong><em>a,b </em>– the most dissimilar diametric points in <em>D</em>

Compute the data mean <em>µ </em>= <em>mean</em>(<em>D</em>);

The algorithm computes the sum of inner products for each pair of points and returns the pair with the lowest such quantity. <strong>(a)[5 pts] </strong>Demonstrate the execution of this algorithm on the following data matrix of 2D instances: D=. Show the steps and the resulting MDD

pair of points.

<strong>(b)[15 pts] </strong>As we discussed in class sometimes we would like to kernelize methods to handle non-linearity in data. Provide a pseudo-code for a kernel version of the MDDP algorithm above. The gole is to kernalize the algorithm for an arbitraty kernel <strong>Hint: Assume that you can compute the kernel matrix </strong><em>K</em><strong>, corresponding to some mapping </strong><em>φ</em>() <strong>and then use the basic kernel operations we discussed in class and also in the book, to derive the steps of MDDP in terms of elements in </strong><em>K</em><strong>.</strong>