## 이진탐색

: 오름차순으로 정렬된 n개의 숫자가 저장된 배열 A에서 어떤 값 x가 배열에 있는지 없는지 `O(log n)` 비교에 알 수 있는 탐색법

### 파이썬코드
```py
def binary_search(A, i, j, x):
  # A[i], ..., A[j]에서 x가 있다면 해당 인덱스를, 없다면 -1을 리턴
  if i > j:
    return -1 # 탐색할 범위가 존재하지 않기 때문에
  m = (i+j)//2
  if x == A[m]: # x를 찾았다!
    return m
  elif x < A[m]: # x가 오른쪽 반에는 없으니, 왼쪽 반 범위에서 탐색 계속함 (재귀호출!)
    return binary_search(A, i, m-1, x)
  else: # x가 왼쪽 반에는 없고, 오른쪽 반 범위에 대해 탐색 계속
    return binary_search(A, m+1, j, x)
```
