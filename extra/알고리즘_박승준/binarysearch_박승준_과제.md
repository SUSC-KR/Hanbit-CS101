```
#include<stdio.h>

int binsearch(int data[], int n, int key){
    int low, high;
    int pivot;
    
    low = 0;
    high = n-1;
    while(low <= high){
        pivot = (low + high)/2;
        if(key == data[pivot]){
            return pivot;
        }
        else if(key < data[pivot]){
            high = pivot - 1;
        }
        else if(key > data[pivot]){
            low = pivot + 1;
        }
    }
    return -1;
}

int main()
{
    int a[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
    int index;
    int key;

    scanf("%d", &key);
    index = binsearch(a,10,key);

    if(index == -1){
        printf("nope");
    }
    else{
        printf("index: %d", index);
    }
}
```
