# Pointer and Array

- 陣列名稱是一個<span style="color:#e5c07b">指標常數</span>，指向陣列中第一個元素的記憶體位址
  >&陣列名稱[索引值] == 陣列名稱 + 索引值

  也就是說
  >陣列名稱[索引值] == *(陣列名稱 + 索引值)  
  
  &nbsp;
  >[!TIP]
  >陣列的位址是唯讀的(常數)，因此不能改變其值

  !FILENAME Example 1
  ```cpp
  int arr[2][3], num1 = 10;
  int *p1 = &num1;

  arr = p1; // invalid
  ```
- 我們可以將指標變數指向陣列的起始位址，並透過反參考運算子(*)來存取陣列中的元素值，以一維陣列為例
  >資料型態 *指標變數 = 陣列名稱;

  或
  >資料型態 *指標變數 = &陣列名稱[0];

- 二維陣列可看成是雙重指標的應用，*(陣列名稱+i)<span style="color:#e5c07b">表示陣列中第一個維度i的第一個元素的記憶體位址</span>，因此
  >&陣列名稱[索引值1][索引值2] == *(陣列名稱+索引值1)+索引值2

  !FILENAME Example 2
  ```cpp
  int arr[2][3] = { {1, 2, 3},  
                    {4, 5, 6} };
  int *p1 = &arr[0][0];
  ```
  !FILENAME Output 2
  ```
  &arr[0][0] = 0x61fef0 , &arr[0][1] = 0x61fef4 , &arr[0][2] = 0x61fef8
  &arr[1][0] = 0x61fefc , &arr[1][1] = 0x61ff00 , &arr[1][2] = 0x61ff04

  *(arr+0) = 0x61fef0 , *(arr+1) = 0x61fefc , *(arr+0)+1 = 0x61fef4

  *(*(arr+0)+1) = 2 , *(*(arr+1)+2) = 6 , *(p1+(1*3)+1) = 5
  ```


&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;