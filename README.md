

## **Experiment: Matrix Operations**

---

### **Aim:To write a program in C++ to input and display a matrix.**

---

### **Tools required : programiz compiler C++**

---


**Q1. Input and Output of a Matrix**

**Theory:**
A matrix is a 3D array of numbers arranged in rows and columns. Inputting a matrix involves reading elements from the user and storing them in a 2D array, while output displays them in tabular form.

**Algorithm:**

1. Start.
2. Read `rows` and `cols`.
3. For each `i` from 0 to rows−1:

   * For each `j` from 0 to cols−1:

     * Input `matrix[i][j]`.
4. For each `i` from 0 to rows−1:

   * For each `j` from 0 to cols−1:

     * Print `matrix[i][j]`.
5. Stop.

**Algorithmic Code:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;
    cout << "Enter rows and columns: ";
    cin >> rows >> cols;
    int a[rows][cols];

    cout << "Enter matrix elements:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cin >> a[i][j];
        }
    }

    cout << "Matrix is:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << a[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
```

---

**Q2. Addition of Matrices**



**Theory:**
Matrix addition is performed by adding corresponding elements of two matrices of equal size.

**Algorithm:**

1. Start.
2. Read `rows` and `cols`.
3. Input matrix A and matrix B.
4. For each `i` from 0 to rows−1:

   * For each `j` from 0 to cols−1:

     * `sum[i][j] = a[i][j] + b[i][j]`.
5. Display `sum` matrix.
6. Stop.

**Algorithmic Code:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;
    cout << "Enter rows and columns: ";
    cin >> rows >> cols;
    int a[rows][cols], b[rows][cols], sum[rows][cols];

    cout << "Enter elements of Matrix A:\n";
    for (int i = 0; i < rows; i++)
        for (int j = 0; j < cols; j++)
            cin >> a[i][j];

    cout << "Enter elements of Matrix B:\n";
    for (int i = 0; i < rows; i++)
        for (int j = 0; j < cols; j++)
            cin >> b[i][j];

    for (int i = 0; i < rows; i++)
        for (int j = 0; j < cols; j++)
            sum[i][j] = a[i][j] + b[i][j];

    cout << "Sum Matrix:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++)
            cout << sum[i][j] << " ";
        cout << endl;
    }
    return 0;
}
```

---

**Q3. Multiplication of Matrices**


**Theory:**
Matrix multiplication is possible only if the number of columns in the first matrix equals the number of rows in the second matrix. Each element of the product matrix is the sum of products of corresponding elements from rows of A and columns of B.

**Algorithm:**

1. Start.
2. Read `n, p` for Matrix A and `r, s` for Matrix B.
3. If `p != r`, print "Not possible" and stop.
4. Input Matrix A and Matrix B.
5. Initialize `product[i][j] = 0`.
6. For each `i` from 0 to n−1:

   * For each `j` from 0 to s−1:

     * For each `k` from 0 to p−1:

       * `product[i][j] += a[i][k] * b[k][j]`.
7. Display `product` matrix.
8. Stop.

**Algorithmic Code:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n, p, r, s;
    cout << "Enter rows and columns of Matrix A: ";
    cin >> n >> p;
    cout << "Enter rows and columns of Matrix B: ";
    cin >> r >> s;

    if (p != r) {
        cout << "Multiplication not possible!";
        return 0;
    }

    int a[n][p], b[r][s], product[n][s] = {0};

    cout << "Enter elements of Matrix A:\n";
    for (int i = 0; i < n; i++)
        for (int j = 0; j < p; j++)
            cin >> a[i][j];

    cout << "Enter elements of Matrix B:\n";
    for (int i = 0; i < r; i++)
        for (int j = 0; j < s; j++)
            cin >> b[i][j];

    for (int i = 0; i < n; i++)
        for (int j = 0; j < s; j++)
            for (int k = 0; k < p; k++)
                product[i][j] += a[i][k] * b[k][j];

    cout << "Product Matrix:\n";
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < s; j++)
            cout << product[i][j] << " ";
        cout << endl;
    }
    return 0;
}
```

---

**Q4. Sum of Diagonal Elements**


**Theory:**
Main diagonal → `i == j`
Secondary diagonal → `i + j == n - 1`
In odd-sized matrices, the center element belongs to both diagonals.

**Algorithm:**

1. Start.
2. Read size `n` (square matrix).
3. Input matrix.
4. Initialize `sumMain = 0`, `sumSecondary = 0`.
5. For `i` from 0 to n−1:

   * `sumMain += a[i][i]`
   * `sumSecondary += a[i][n - i - 1]`
6. Display sums.
7. Stop.

**Algorithmic Code:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter size of square matrix: ";
    cin >> n;
    int a[n][n], sumMain = 0, sumSecondary = 0;

    cout << "Enter elements:\n";
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n; j++)
            cin >> a[i][j];

    for (int i = 0; i < n; i++) {
        sumMain += a[i][i];
        sumSecondary += a[i][n - i - 1];
    }

    cout << "Main Diagonal Sum: " << sumMain << endl;
    cout << "Secondary Diagonal Sum: " << sumSecondary << endl;
    return 0;
}
```

---

**Q5. Transpose of a Matrix**



**Theory:**
The transpose of a matrix is obtained by interchanging its rows with columns: `B[i][j] = A[j][i]`.

**Algorithm:**

1. Start.
2. Read `rows` and `cols`.
3. Input matrix.
4. For each `i` from 0 to rows−1:

   * For each `j` from 0 to cols−1:

     * `transpose[j][i] = a[i][j]`.
5. Display transpose.
6. Stop.

**Algorithmic Code:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;
    cout << "Enter rows and columns: ";
    cin >> rows >> cols;
    int a[rows][cols], transpose[cols][rows];

    cout << "Enter elements:\n";
    for (int i = 0; i < rows; i++)
        for (int j = 0; j < cols; j++)
            cin >> a[i][j];

    for (int i = 0; i < rows; i++)
        for (int j = 0; j < cols; j++)
            transpose[j][i] = a[i][j];

    cout << "Transpose Matrix:\n";
    for (int i = 0; i < cols; i++) {
        for (int j = 0; j < rows; j++)
            cout << transpose[i][j] << " ";
        cout << endl;
    }
    return 0;
}
```

---

### **Conclusion**

In this experiment, we learned to:

* Take input and display matrices.
* Perform addition and multiplication of matrices.
* Calculate the sum of diagonal elements.
* Find the transpose of a matrix.

These operations are fundamental in numerical computing and have applications in engineering, graphics, and data science.

