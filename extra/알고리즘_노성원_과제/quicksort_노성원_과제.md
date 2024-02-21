## QUICK SORT
<br>quick sort란 분할 정복 알고리즘 중 하나로, 피벗을 기준으로 큰 값과 작은 값을 서로 교체하는 정렬 기법이다.</br> 값을 서로 교체하는 데에 N번, 엇갈린 경우 교체 이후에 원소가 반으로 나누어지므로 전체 원소를 나누는 데에 평균적으로 logN번이 소요되므로, 
평균적으로  O(N * log N)의 시간복잡도를 가진다.
```cpp
#include <iostream>
using namespace std;
int arr[6] = {2, 9, 3, 7, 6, 8};
void quickSort(int arr[], int first, int last){
	if(first >= last) {
            return;
        }
	int pivot = first;
	int i = first + 1;//왼쪽 출발
	int j = last;//오른쪽 출발
	int tmp;

	while (i <= j){
		while (arr[i] < arr[pivot] && i <= last){
                    i++;
                }  
		while (arr[j] >= arr[pivot] && j > first) {
                    j--;
                }
		if (i >= j) break;

		tmp = arr[i];
		arr[i] = arr[j];
		arr[j] = tmp;
	}

	tmp = arr[j];
	arr[j] = arr[pivot];
	arr[pivot] = tmp;

	quickSort(arr, first, j - 1);//왼쪽 정렬
	quickSort(arr, j + 1, last);//오른쪽 정렬
}

```
