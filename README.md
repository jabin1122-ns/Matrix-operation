# Matrix-operation
#include <stdio.h>

int main() {
    int size;

    // Input size of the matrix
    printf("Enter the size of the square matrices (e.g., 3 for 3x3): ");
    scanf("%d", &size);

    int A[size][size], B[size][size];
    int sum[size][size], diff[size][size], product[size][size];

    // Input Matrix A
    printf("\nEnter elements of Matrix A (%dx%d):\n", size, size);
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            printf("A[%d][%d]: ", i, j);
            scanf("%d", &A[i][j]);
        }
    }

    // Input Matrix B
    printf("\nEnter elements of Matrix B (%dx%d):\n", size, size);
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++) {
            printf("B[%d][%d]: ", i, j);
            scanf("%d", &B[i][j]);
        }
    }

    // Matrix Addition
    for (int i = 0; i < size; i++)
        for (int j = 0; j < size; j++)
            sum[i][j] = A[i][j] + B[i][j];

    // Matrix Subtraction
    for (int i = 0; i < size; i++)
        for (int j = 0; j < size; j++)
            diff[i][j] = A[i][j] - B[i][j];

    // Matrix Multiplication
    for (int i = 0; i < size; i++)
        for (int j = 0; j < size; j++) {
            product[i][j] = 0;
            for (int k = 0; k < size; k++)
                product[i][j] += A[i][k] * B[k][j];
        }

    // Output
    printf("\nSum of A and B:\n");
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++)
            printf("%4d", sum[i][j]);
        printf("\n");
    }

    printf("\nDifference of A and B:\n");
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++)
            printf("%4d", diff[i][j]);
        printf("\n");
    }

    printf("\nProduct of A and B:\n");
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < size; j++)
            printf("%4d", product[i][j]);
        printf("\n");
    }

    return 0;
}

