# Dynamic Memory Allocation

- 在執行階段時，依照資料型態來動態配置一個記憶體空間，若配置成功，會把<span style="color:#e5c07b">配置空間位址</span>傳回指派的指標變數；若失敗，則傳回<span style="color:#e5c07b">NULL</span>  
  >資料型態 \*指標變數 = new 資料型態(初始值); *(可不指定初始值)*

- 當配置的記憶體已不再使用時，必須以delete運算子來釋放該記憶體空間
  >delete 指標名稱;

  &nbsp;
  >[!TIP]
  >若指向動態配置空間的指標在未釋放該位址空間前，又指向別的記憶體空間，則原本所指向的空間將無法被釋放，造成記憶體缺口

  !FILENAME Example 1
  ```cpp
  int *ptr1 = new int(10);
  int *ptr2 = new int(41);

  cout << ptr1 << endl;
  cout << ptr2 << endl;
  cout << *ptr1 + *ptr2 << endl;

  delete ptr1;
  delete ptr2;

  // 使用delete釋放動態陣列後，最好將此指標變數指向NULL
  ptr1 = NULL; 
  ptr2 = NULL;
  ```
  !FILENAME Output 1
  ```
  Line 04: 0x10b1858
  Line 05: 0x10b1868
  Line 06: 51
  ```

- 動態配置及釋放一維陣列的方式如下，此時指標變數指向陣列第一個元素的位址
  >資料型態 *指標變數 = new 資料型態[元素個數];
  >delete [] 指標變數;

  !FILENAME Example 2
  ```cpp
  int *ptr = new int[3];

  ptr[0] = 2;
  ptr[1] = 3;
  ptr[2] = 5;

  for(int i = 0; i < 3; i++){
      cout << *(ptr+i) << ' ' << ptr+i << endl;
  }

  delete [] ptr;
  ptr = NULL;
  ```
  !FILENAME Output 2
  ```
  Line 08: 2 0x10b1858
          3 0x10b185c
          5 0x10b1860
  ```