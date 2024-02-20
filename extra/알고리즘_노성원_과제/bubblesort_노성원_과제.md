## BUBBLE SORT
버블 정렬(bubble sort)란 서로 이웃한 데이터들을 비교하여 큰 데이터를 뒤로 보내는 과정을 반복하여 정렬하는 방식이다.
앞에서부터 두개씩 비교/배열의 가장 마지막 원소부터 하나씩 정리된다. n개의 데이터를 정렬할 때 탐색하는 과정에서 O(N)이 걸리고 n-1번동안 정렬하므로 총 시간복잡도는 O(N^2)이다.
```cpp
#include<iostream>
using namespace std;
 
int main() {
	int arr[5] = { 5,1,4,7,2 };
	int temp;
 
	for (int i = 0; i < 4; i++) {
		for (int j = 0; j < 4 - i; j++) {
			if (arr[j] > arr[j + 1]) {
				temp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
			}
		}

	for (int i = 0; i < 5; i++) {
		cout << arr[i] << " ";
	}

	return 0;
}
```
