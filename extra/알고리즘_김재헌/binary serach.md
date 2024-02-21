#include <stdio.h>
 
int binsearch(int data[], int n, int key);
 
int main(int argc, char *argv[])
{
    int a[10] = { 2, 8, 13, 16, 20, 22, 34, 45, 56, 77 };    //정렬된 자료
    int index;
    int key;
 
    scanf("%d", &key);
    index = binsearch(a, 10, key);
    if (index == -1) {
        printf("자료가 없습니다!\n");
    }
    else {
        printf("자료가 %d번째에 있습니다.\n", index + 1);
    }
    return 0;
}
