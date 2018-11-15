title: Sparse Matricies
date: 2018-11-15 14:44:30
tags:
---
There are many situations where a very large matrix is necessary, conviently there are many times that this matrix is a sparse matrix. Inorder to store and operate on large sparce matricies we utilize new systems of data storage that minimize the memory consumed by the storage of an extreamly large space matrix.

<!-- more -->

We will use the example case of a matrix of one million by one million to demonstrate the memory efficiency of the data structures. We will also assume that the data in the matrix requires 8 bytes as well as the index variables. We will say that the matrix is \\(p\\) sparce, where \\(p\\) denotes the percentage of non zero elements in the matrix.


# Full Matrix #

The first method is to store the entierty of the matrix. With many of the elements being zero. This method will require \\(N\times N\\) elements of data to be stored. And thus it is not very efficient for very sparse matricies. For our test example we can find the number of GB of memory required to store it.

$$
\left(10^6\cdot10^6\right)\cdot 8 = 8\times10^{12}\text{bytes}=8,000\text{GB}
$$

This is an unacceptable amout of memory required to store this information, as with highly sparsed matricies, there could be only a few thousand values that are not zero. This is where we begin our first optimizations.

# Dictionary of Keys #

This is the first logical step in memory optimization. Instead of storing all elements of the matrix, we will instead store a list of three value tuples. The first two values are the row and column position in the matrix, and the final value is the value stored at that position.

This means that for every non zero element in our matrix we must store three values. The row, column, and the value itself. Again using our test case we find the number of GB.

$$
\left(10^6\cdot10^6\right)\cdot p \cdot (3\cdot8)
$$