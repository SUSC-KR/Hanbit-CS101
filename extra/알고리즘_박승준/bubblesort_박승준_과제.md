#include<stdio.h>
int main()
{
    int arr[5] = {7, 5, 1, 4, 3};
    int temp=0;
    
    printf("before sort: ");
    for(int i=0;i<5;i++){
        printf("%d ", arr[i]);
    }
    printf("\n");

    for(int i=0;i<5;i++){
        for(int j=0;j<5-i-1;j++){
            if(arr[j]>arr[j+1]){
                temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
                
                // for(int i=0;i<5;i++){
                //     printf("%d ", arr[i]);
                // }
                // printf("\n");
                // bubble sort 하는 과정을 보는 줄
            }
        }
    }

    printf("after sort: ");
    for(int i=0;i<5;i++){
        printf("%d ", arr[i]);
    }
}
