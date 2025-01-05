# Introduction to Pointer

- 變數位址的存取
  >&變數名稱;
  
- 指標變數(pointer variable)是一種用來<span style="color:#e5c07b">儲存記憶體位址的變數</span>，宣告方式
  >資料型態 \*指標變數 = NULL;(NULL可省略)  
  >指標變數 = &變數名稱;

  或
  >資料型態 \*指標變數 = &變數名稱;

- 若指標變數已經指向了一個宣告過的變數位址時，則可透過反參考運算子(*)重新指定指標變數的資料內容
  >\*指標變數 = 數值;

  !FILENAME Example 1
  ```cpp
  int num1 = 10;
  int *p1;

  p1 = &num1;
  *p1 = 41;
  ```
  !FILENAME Output 1
  ```
  Line 04: p1 = 0x61ff08 , num1 = 10
  Line 05: p1 = 0x61ff08 , num1 = 41
  ```
- 指標變數的加減法運算用於增減記憶體位址的<span style="color:#e5c07b">位移量</span>
  
  >[!TIP]
  >1. 指標運算只能針對常數(如+1或-1)來進行，不可做指標變數彼此間的運算  
  >2. 相同型態的指標變數可利用比較運算子來比較位址的先後

  !FILENAME Example 2
  ```cpp
  int num1 = 10;      // int 4-bit
  int *p1 = &num1;
  double num2 = 3.14; // double 8-bit
  double *p2 = &num2;

  p1++;
  p2++;

  p1 -= 3;
  p2 -= 3;
  ```
  !FILENAME Output 2
  ```
  Line 04: p1 = 0x61ff04 , p2 = 0x61fef8
  Line 07: p1 = 0x61ff08 , p2 = 0x61ff00
  Line 10: p1 = 0x61fefc , p2 = 0x61fee8
  ```
- 指標變數本身佔有記憶體空間，也有一個地址，因此可以宣告<span style="color:#e5c07b">指向指標變數的指標變數</span>
  
  !FILENAME Example 3
  ```cpp
  int num1 = 10;
  int *p1 = &num1; // 定義指標變數*p1，指向整數變數num的位址
  int **p2 = &p1;  // 定義指標變數**p2，指向指標變數p1的位址
  ```
  !FILENAME Output 3
  ```
  Line 02: p1 = 0x61ff08 , *p1 = 10
  Line 03: p2 = 0x61ff04 , *p2 = 0x61ff08 , **p2 = 10 , &p2 = 0x61ff00
  ```

  變數名稱 |儲存值  |記憶體位址  
  :---:   |:---:   |:---:  
  num     |10      |61ff08  
  p1      |61ff08  |61ff04  
  p2      |61ff04  |61ff00  

&nbsp;
&nbsp;
&nbsp;
&nbsp;   
