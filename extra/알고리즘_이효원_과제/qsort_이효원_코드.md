## Quick Sort

: 말 그대로 빠른 정렬 / 합병 정렬처럼 문제를 쪼개서 정렬하는 방식

맨 앞의 값을 임의로 pivot이고 설정, pivot을 기준으로 배열을 나눔

예를 들어, (24,	26,	2, 16, 32, 31, 25)일 때 
1. pivot = 24, low  = [2, 16], high = [26, 32, 31, 25]
2. pivot1 = 2, low = [ ], high = [16] / pivot = 26, low = [25], high = [32, 31]

.... low와 high에 원소가 2개 미만이 될 때까지

-> [24, 26, 2, 16, 32, 31, 25] 정렬 과정
1. [2, 16] + [24] + [26, 32, 31, 25] : 첫 번째 분할
2. [] + [2] + [16]                   : 왼쪽 부분 배열 [2, 16]을 분할. 정렬 완료
3. [25] + [26] + [32, 31]            : 오른쪽 부분 배열 [26, 32, 31, 25]를 분할
4. [31] + [32] + [ ]                  : 바로 위의 왼쪽 부분 배열은 정렬 끝, 오른쪽 부분 배열을 분할. 역시 정렬 끝
5. [2, 16, 24, 25, 26, 31, 32]       : 분할한 모든 배열을 결합한 최종 결과

### 파이썬코드
```py
def qsort(arr):
  if len(arr) < 2:
    return arr
  pivot = arr[0]
  low = []
  high = []
  for value in arr[1:]:
    if value < pivot:
      low.append(value)
    else:
      high.append(value)

  return qsort(low) + [pivot] + qsort(high)
```
