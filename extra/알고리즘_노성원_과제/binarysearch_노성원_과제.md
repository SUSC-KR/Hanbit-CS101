## 이진 탐색(binary search)
이진 탐색은 정렬된 데이터를 반으로 쪼개면서 탐색하므로 데이터를 반으로 쪼개면서 탐색하므로 데이터를 빠르게 탐색한다.
```cpp
#include <iostream>
using namespace std;
int arr[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
// 이진 탐색 함수
int binarySearch(int* arr, int target) {
    int left = 0;
    int right = arr.size() - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;

        // 중간 값이 타겟과 같으면 인덱스 반환
        if (arr[mid] == target)
            return mid;

        // 중간 값이 타겟보다 작으면 오른쪽 부분 탐색
        else if (arr[mid] < target)
            left = mid + 1;

        // 중간 값이 타겟보다 크면 왼쪽 부분 탐색
        else
            right = mid - 1;
    }
    // 타겟을 찾지 못한 경우
    return -1;
}
```
