Q1) 입력, 출력, 정확성, 유한성, 효율성, 일반성, 확장성


Q2)

순차구조: 순차적으로 실행하는 구조이다. 

선택구조: if문과 같은 조건식이 들어가 참일 때와 거짓일 때 돌아가는 코드를 선택해서 실행시킬 수 있다. 

반복구조: while for문과 같이 특정 문장들을 반복해서 실행하는 문장 구조이다


Q3) 선택 정렬, 삽입 정렬, 버블 정렬이 있고, 탐색에는 선형 탐색, 이진 탐색이 있다.

Q4)

```
Algorithm bubble(int ds[], int n) {
	for i = 1 to n-2
		for j = 1 to n-i
			if ds[j-1] > ds[j]
				temp = ds[j-1]
				ds[j-1] = ds[j]
				ds[j] = temp
			end if
		next j
	next i
}
```

Q5)

```
Algorithm binary(int ds[], int n){
	low = 0
	high = n-1
	
	input key
	while low <= high
		mid = (low + high) / 2
		if key == ds[mid]
			return mid
		else if key < ds[mid]
			high = mid -1
		else
			low = mid +1
		end if
	end while
}
```
