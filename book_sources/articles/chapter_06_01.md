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

> [!TIP]
> An alert of type 對於指標的加減運算.