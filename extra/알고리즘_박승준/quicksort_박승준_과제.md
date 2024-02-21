```
#include <stdio.h>

void QuickSort(int arr[], int left, int right)
{
    int L = left, R = right;
    int temp;
    int pivot = arr[(L + R) / 2];

    while (L <= R)
    {
        while (arr[L] < pivot) L++;
        while (arr[R] > pivot) R--;
        if (L <= R)
        {
            if (L != R)
            {
                temp = arr[L];
                arr[L] = arr[R];
                arr[R] = temp;
            }
            L++;
            R--;
        }
    }
    if (L < right) QuickSort(arr, L, right);
    if (R > left) QuickSort(arr, left, R);
}

int main()
{
    int arr[10] = {5, 3, 7, 6, 1, 9, 0, 2, 8, 4};

    QuickSort(arr, 0, 9);

    for (int i = 0; i < 10; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```
