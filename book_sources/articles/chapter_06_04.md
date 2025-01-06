# Introduction to Reference

- 參考型態可以用來替變數、常數或物件取<span style="color:#e5c07b">別名(alias)</span>，一旦對變數或物件(B)取了別名(A)，則<span style="color:#e5c07b">所有作用於A的運算處理所產生的效果都會累積到B身上</span>  
  >資料型態 &參考名稱 = 初始值;

  !FILENAME Example 1
  ```cpp
  int num = 41;
  int &ref = num;
  int *ptr = &num;

  num += 10;
  *ptr += 10; // pointer operation
  ref += 10;  // reference operation
  ```
  !FILENAME Output 1
  ```
  Line 03: num = 41 , ref = 41 , *ptr = 41
  Line 05: num = 51 , ref = 51 , *ptr = 51
  Line 06: num = 61 , ref = 61 , *ptr = 61
  Line 07: num = 71 , ref = 71 , *ptr = 71
  ```