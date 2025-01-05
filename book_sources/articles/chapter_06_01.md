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
int* p1;

p1 = &num1;
*p1 = 41;
```
!FILENAME Output 1
```
Line 4: p1 = 0x61ff08 , num1 = 10
Line 5: p1 = 0x61ff08 , num1 = 41
```
- 指標變數的加減法運算用於增減記憶體位址的<span style="color:#e5c07b">位移量</span>
  
  >[!TIP]
  >1. 指標運算只能針對常數(如`+1`或`-1`)來進行，不可做指標變數彼此間的運算  
  >2. 相同型態的指標變數可利用比較運算子來比較位址的先後


- 指標變數本身也佔有記憶體空間，也有一個地址，因此可以宣告<span style="color:#e5c07b">指向指標變數的指標變數</span>
&nbsp;
&nbsp;
&nbsp;
&nbsp;

