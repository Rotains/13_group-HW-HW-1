#include <stdio.h>

//최대값 구하는 함수

int Max(int* pArr, int size) {

    int max = pArr[0];
    for (int i = 1; i < size; ++i) {
        if (pArr[i] > max) {
            max = pArr[i];
        }
    }
    return max;
}

//최소값 구하는 함수

int Min(int* pArr, int size) {

    int min = pArr[0];
    for (int i = 1; i < size; ++i) {
        if (pArr[i] < min) {
            min = pArr[i];
        }
    }
    return min;
}

//내림차순 정렬하는 함수

void Sorting(int* pArr, int size) {

    int temp;
    for (int i = 0; i < size - 1; ++i) {
        for (int j = i + 1; j < size; ++j) {
            if (pArr[i] < pArr[j]) {
                temp = pArr[i];
                pArr[i] = pArr[j];
                pArr[j] = temp;
            }
        }
    }
}

int main() {

    int b[] = { 20, 34, 12, 24, 54, 91, 9, 40, 81, 10 };
    int size = sizeof(b) / sizeof(b[0]);

    printf("[정렬 전 배열]\n");
    for (int i = 0; i < size; ++i) {
        printf("%d, ", b[i]);
    }
    printf("\n");

    printf("[최대값]: %d\n", Max(b, size));
    printf("[최소값]: %d\n", Min(b, size));

    Sorting(b, size);

    printf("[내림차순 정렬 후 배열]\n");
    for (int i = 0; i < size; ++i) {
        printf("%d, ", b[i]);
    }
    printf("\n");

    return 0;
}
