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
- 字串是由字元陣列組成，可以透過指標來宣告及操作
  >**const** char *指標變數 = "字串內容"; // 加上const才不會有warning

  !FILENAME Example 3
  ```cpp
  char arr[] = "Almond";
  char *p1 = arr;

  cout << (int *)p1 << endl; //輸出p1所指向的位址
  cout << p1 << endl;

  arr += 2; // invalid, arr為指標常數
  p1 += 2;

  cout << (int *)p1 << endl;
  cout << p1 << endl;
  ```
  !FILENAME Output 3
  ```
  Line 04: 0x61ff05
  Line 05: Almond
  Line 10: 0x61ff07
  Line 11: mond
  ```
- 指標也可像其他變數一樣，宣告為陣列的形式，稱為<span style="color:#e5c07b">指標陣列</span>
  >資料型態 *陣列名稱[陣列大小];

  而字串陣列可用二維字元陣列或是<span style="color:#e5c07b">一維字串指標陣列</span>儲存

  !FILENAME Example 4
  ```cpp
  const char *p1[4] = {"Almond","Breadfruit","Citron","Dragon fruit"};
  char arr[4][13] = {"Almond","Breadfruit","Citron","Dragon fruit"};

  for(int i = 0; i < 4; i++){
        cout << (int *)p1[i] << ' ' << p1[i] << endl;
  }
  for(int i = 0; i < 4; i++){
        cout << (int *)arr[i] << ' ' << arr[i] << endl;
  }
  ```
  !FILENAME Output 4
  ```
  Line 05: 0x605065 Almond
           0x40506c Breadfruit
           0x405077 Citron
           0x40507e Dragon fruit

  Line 08: 0x61fec4 Almond
           0x61fed1 Breadfruit
           0x61fede Citron
           0x61feeb Dragon fruit
  ```