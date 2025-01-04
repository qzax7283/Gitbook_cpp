# Introduction to Pointer

這是第一章的內容

編輯第一章 blahblah

```cpp
#include <iostream>

using namespace std;

int main(){
    int arr[] = {10, 20, 30, 40};

    cout << "arr[1]\t\t" << arr[1] << endl;
    cout << "*(arr+1)\t" << *(arr+1) << endl;
    cout << "*(&arr[1])\t" << *(&arr[1]) << endl << endl;

    int arr2d[4][3] = {{1, 2, 3},
                       {4, 5, 6},
                       {7, 8, 9},
                       {10, 11, 12}};

    cout << "arr2d\t\t" << arr2d << endl;
    cout << "arr2d+1\t\t" << arr2d+1 << endl;
    cout << "*(arr2d+0)\t" << *(arr2d+0) << endl;
    cout << "*(arr2d+1)\t" << *(arr2d+1) << endl;
    cout << "*(arr2d+0)+1\t" << *(arr2d+0)+1 << endl;
    cout << "*(*(arr2d+0)+1)\t" << *(*(arr2d+0)+1) << endl;
    cout << "*(*(arr2d+3)+2)\t" << *(*(arr2d+3)+2) << endl;
   


    return 0;
}
```