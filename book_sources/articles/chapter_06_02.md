# Pointer and Array

- 陣列名稱是一個<span style="color:#e5c07b">指標常數</span>，指向陣列中第一個元素的記憶體位址
  >&陣列名稱[索引值] == 陣列名稱 + 索引值

  也就是說
  >陣列名稱[索引值] == *(陣列名稱 + 索引值)  

  >[!TIP]
  >陣列的位址是唯讀的(常數)，因此不能改變其值

  !FILENAME Example 1
  ```cpp
  int arr[2][3], num1 = 10;
  int *p1 = &num1;

  arr = p1; // invalid
  ```