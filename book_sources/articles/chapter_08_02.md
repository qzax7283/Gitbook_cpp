# Structure Array

- 若要同時記錄多筆相同結構的資料，可以宣告一個<span style="color:#e5c07b">結構陣列型態</span>
  >struct 結構型態名稱 結構陣列名稱[陣列長度];

- 存取結構陣列成員的方式
  >結構型態名稱[索引值].結構陣列成員名稱

  或是使用<span style="color:#e5c07b">指標常數</span>運算的觀念來存取
  >(結構型態名稱+i) -> 結構陣列成員名稱

- 結構成員也可宣告成<span style="color:#e5c07b">陣列</span>的形式，存取結構陣列成員的陣列元素方式
  >結構陣列名稱[索引值].結構陣列成員名稱[索引值]

- 我們也可以把結構宣告成<span style="color:#e5c07b">指標陣列</span>的形式，使得陣列中的每個元素存放的都是指標
  >struct 結構型態名稱 *結構指標陣列名稱[陣列長度];

  &nbsp;
  >[!TIP]
  >由於結構指標陣列中存放的是位址，因此存取其指向的結構成員位置方式為  
  >{arr[i] -> member}而非{*arr[i].member}或是{(arr+i) -> member} 

  !FILENAME Example 1
  ```cpp
  struct fruit{
    char name[15];
    int sales[3]; // 結構的陣列成員
  };
  // 結構陣列
  struct fruit var[4] = { {"almond", 43, 47, 27},
                          {"breadfruit", 12, 17, 16},
                          {"citron", 22, 19, 35},
                          {"dragon fruit", 11, 14, 13} }; 

  struct fruit *ptr[4]; // 結構指標陣列

  for(int i = 0; i < 4; i++){
      ptr[i] = &var[i];
  }

  cout << var[1].name << endl;
  cout << var[3].sales[1] << endl;
  cout << (var + 2) -> name << endl;
  cout << ptr[0] -> sales[2] << endl;
  ```
  !FILENAME Output 1
  ```
  Line 17: breadfruit
  Line 18: 14
  Line 19: citron
  Line 20: 27
  ```