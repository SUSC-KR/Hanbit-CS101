Bubble sort 구현

# include <stdio.h>
# define MAX_SIZE 5

// 버블 정렬
void bubble_sort(int list[], int n){
  int i, j, temp;

  for(i=n-1; i>0; i--){
    // 0 ~ (i-1)까지 반복
    for(j=0; j<i; j++){
      // j번째와 j+1번째의 요소가 크기 순이 아니면 교환
      if(list[j]<list[j+1]){
        temp = list[j];
        list[j] = list[j+1];
        list[j+1] = temp;
      }
    }
  }
}

void main(){
  int i;
  int n = MAX_SIZE;
  int list[n] = {7, 4, 5, 1, 3};

  // 버블 정렬 수행
  bubble_sort(list, n);

  // 정렬 결과 출력
  for(i=0; i<n; i++){
    printf("%d\n", list[i]);
  }
}


quick sort 구현

#include <stdio.h> 
#define SIZE 1000

int a[SIZE];

void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

void quickSort(int start, int end) {
    if (start >= end) return;
    int key = start, i = start + 1, j = end, temp;
    while (i <= j) {
        while (i <= end && a[i] <= a[key]) i++; 
        while (j > start && a[j] >= a[key]) j--;
        
        if (i > j) swap(&a[key], &a[j]);
        else swap(&a[i], &a[j]);
    }
    
    quickSort(start, j - 1);
    quickSort(j + 1, end); 
}

int main(void) {
    int n;
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }
    quickSort(0, n - 1);
    for (int i = 0; i < n; i++) {
        printf("%d ", a[i]);
    }
}
