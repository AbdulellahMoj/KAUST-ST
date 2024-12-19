
# Linear Algebra Revision for Machine Learning

## Part 1: Basics of Linear Algebra

### 1.1 Scalars, Vectors, and Matrices

- **Scalars**: A single number (e.g., \( a = 5 \)).
- **Vectors**: A 1D array of numbers, e.g., \( \mathbf{v} = egin{bmatrix} 2 \ 3 \ 5 \end{bmatrix} \).
- **Matrices**: A 2D array of numbers, e.g., 
  \[
  \mathbf{A} = egin{bmatrix} 1 & 2 \ 3 & 4 \end{bmatrix}
  \]

#### Example: Matrix Addition
\[
\mathbf{A} = egin{bmatrix} 1 & 2 \ 3 & 4 \end{bmatrix}, \quad \mathbf{B} = egin{bmatrix} 2 & 3 \ 4 & 5 \end{bmatrix}
\]
\[
\mathbf{A} + \mathbf{B} = egin{bmatrix} 1+2 & 2+3 \ 3+4 & 4+5 \end{bmatrix} = egin{bmatrix} 3 & 5 \ 7 & 9 \end{bmatrix}
\]

### 1.2 Vector Operations

- **Dot Product**: \( \mathbf{u} \cdot \mathbf{v} \)
- **Norm**: \( \| \mathbf{v} \|_2 = \sqrt{v_1^2 + v_2^2 + \cdots + v_n^2} \)

#### Example: Dot Product
\[
\mathbf{u} = egin{bmatrix} 1 \ 2 \end{bmatrix}, \quad \mathbf{v} = egin{bmatrix} 3 \ 4 \end{bmatrix}
\]
\[
\mathbf{u} \cdot \mathbf{v} = (1)(3) + (2)(4) = 3 + 8 = 11
\]

### 1.3 Matrix Multiplication
- Multiply rows of the first matrix with the columns of the second matrix.

#### Example: Matrix Multiplication
\[
\mathbf{A} = egin{bmatrix} 1 & 2 \ 3 & 4 \end{bmatrix}, \quad \mathbf{B} = egin{bmatrix} 5 & 6 \ 7 & 8 \end{bmatrix}
\]
\[
\mathbf{A} \mathbf{B} = egin{bmatrix} (1)(5) + (2)(7) & (1)(6) + (2)(8) \ (3)(5) + (4)(7) & (3)(6) + (4)(8) \end{bmatrix} = egin{bmatrix} 19 & 22 \ 43 & 50 \end{bmatrix}
\]

---

## Part 2: Matrix Inverses and Transposes

### 2.1 Matrix Transpose

- Interchanging rows and columns of a matrix.

#### Example: Transpose of a Matrix
\[
\mathbf{A} = egin{bmatrix} 1 & 2 \ 3 & 4 \end{bmatrix}, \quad \mathbf{A}^T = egin{bmatrix} 1 & 3 \ 2 & 4 \end{bmatrix}
\]

### 2.2 Inverse of a Matrix

For a square matrix \( \mathbf{A} \), the inverse \( \mathbf{A}^{-1} \) is defined such that:
\[
\mathbf{A} \mathbf{A}^{-1} = \mathbf{I}
\]
Where \( \mathbf{I} \) is the identity matrix.

#### Example: Inverse of a Matrix
\[
\mathbf{A} = egin{bmatrix} 1 & 2 \ 3 & 4 \end{bmatrix}, \quad \mathbf{A}^{-1} = rac{1}{(1)(4)-(2)(3)} egin{bmatrix} 4 & -2 \ -3 & 1 \end{bmatrix} = egin{bmatrix} -2 & 1 \ 1.5 & -0.5 \end{bmatrix}
\]

---

## Part 3: Eigenvalues and Eigenvectors

- **Eigenvalue Equation**: \( \mathbf{A} \mathbf{v} = \lambda \mathbf{v} \)

#### Example: Finding Eigenvalues and Eigenvectors
For matrix \( \mathbf{A} = egin{bmatrix} 4 & 1 \ 2 & 3 \end{bmatrix} \), we solve:
\[
	ext{det}(\mathbf{A} - \lambda \mathbf{I}) = 0
\]
This gives eigenvalues \( \lambda_1 = 5 \), \( \lambda_2 = 2 \).

---

## Part 4: Matrix Factorizations

### 4.1 LU Decomposition
Decompose \( \mathbf{A} \) into a lower triangular matrix \( \mathbf{L} \) and an upper triangular matrix \( \mathbf{U} \).

#### Example: LU Decomposition
\[
\mathbf{A} = egin{bmatrix} 2 & 3 \ 4 & 7 \end{bmatrix}, \quad L = egin{bmatrix} 1 & 0 \ 2 & 1 \end{bmatrix}, \quad U = egin{bmatrix} 2 & 3 \ 0 & 1 \end{bmatrix}
\]

### 4.2 QR Decomposition

Factor a matrix \( \mathbf{A} \) into an orthogonal matrix \( \mathbf{Q} \) and an upper triangular matrix \( \mathbf{R} \).

---

## Part 5: Singular Value Decomposition (SVD)

For any matrix \( \mathbf{A} \), SVD decomposes it into three matrices:
\[
\mathbf{A} = \mathbf{U} \Sigma \mathbf{V}^T
\]

#### Example: SVD of a Matrix
\[
\mathbf{A} = egin{bmatrix} 1 & 0 \ 0 & -2 \end{bmatrix}, \quad \mathbf{U} = \mathbf{I}, \quad \Sigma = egin{bmatrix} 1 & 0 \ 0 & 2 \end{bmatrix}, \quad \mathbf{V}^T = egin{bmatrix} 1 & 0 \ 0 & -1 \end{bmatrix}
\]

---

## Part 6: Principal Component Analysis (PCA)

### 6.1 Steps to Perform PCA

1. **Standardize the data**.
2. **Compute the covariance matrix**.
3. **Find the eigenvalues and eigenvectors** of the covariance matrix.
4. **Project the data** onto the principal components.

#### Example: PCA
For a dataset:
\[
X = egin{bmatrix} 2 & 4 \ 3 & 5 \ 5 & 7 \end{bmatrix}
\]
We can compute the principal components after standardization and eigenvalue decomposition.

---

## Practice Problems

### Problem 1: Matrix Multiplication
Compute the product of the following matrices:
\[
\mathbf{A} = egin{bmatrix} 2 & 0 \ 1 & 3 \end{bmatrix}, \quad \mathbf{B} = egin{bmatrix} 4 & 1 \ 0 & 2 \end{bmatrix}
\]

### Problem 2: Eigenvalue Calculation
Find the eigenvalues of the following matrix:
\[
\mathbf{A} = egin{bmatrix} 3 & 1 \ 1 & 3 \end{bmatrix}
\]

### Problem 3: SVD Decomposition
Perform SVD on the matrix:
\[
\mathbf{A} = egin{bmatrix} 1 & 0 \ 0 & -3 \end{bmatrix}
\]

---

## Solutions

### Solution 1: Matrix Multiplication
\[
\mathbf{A} \mathbf{B} = egin{bmatrix} (2)(4) + (0)(0) & (2)(1) + (0)(2) \ (1)(4) + (3)(0) & (1)(1) + (3)(2) \end{bmatrix} = egin{bmatrix} 8 & 2 \ 4 & 7 \end{bmatrix}
\]

### Solution 2: Eigenvalue Calculation
Eigenvalues are \( \lambda_1 = 4 \), \( \lambda_2 = 2 \).

### Solution 3: SVD
SVD of the matrix gives:
\[
\mathbf{U} = \mathbf{I}, \quad \Sigma = egin{bmatrix} 1 & 0 \ 0 & 3 \end{bmatrix}, \quad \mathbf{V}^T = egin{bmatrix} 1 & 0 \ 0 & -1 \end{bmatrix}
\]

