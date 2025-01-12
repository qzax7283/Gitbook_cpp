# Parameter Passing of Functions

- 函數的原型(prototype)宣告
  >回傳資料型態 函數名稱(資料型態 參數1, 資料型態 參數2, ...);

  或
  >回傳資料型態 函數名稱(資料型態, 資料型態, ...);

- 函數是由函數名稱、參數、回傳值與回傳資料型態組成
  >回傳資料型態 函數名稱(參數列){  
  >&nbsp;&nbsp;&nbsp;&nbsp;程式敘述區塊;  
  >&nbsp;&nbsp;&nbsp;&nbsp;return 回傳值;  
  >}

  &nbsp;
  >[!TIP]
  >1. 參數列必須包含資料型態和參數名稱  
  >2. 若函數沒有回傳值，可以省略return敘述

- 直接使用函數名稱即可呼叫函數
  >函數名稱(引數1, 引數2, ...);

  若函數不需要傳入參數
  >函數名稱();  
  >or   
  >函數名稱(void);

  若函數有回傳值
  >變數 = 函數名稱(引數1, 引數2, ...);

- 函數參數的種類分為以下兩種：  
&nbsp;1. <span style="color:#e5c07b">形式參數(Formal Parameter)</span>：在函數定義標頭中所宣告的參數  
&nbsp;2. <span style="color:#e5c07b">實際參數(Actual Parameter)</span>：實際呼叫函數時所提供的參數  

- 對於傳遞參數的方式，可以根據傳遞和接收的是參數數值或參數位址分為三種  
  ##### <span style="color:#e5c07b">1. 傳值呼叫(call by value)</span>
  將實際參數的數值<span style="color:#e5c07b">複製一份</span>給函數中相對應的形式參數，形式參數是額外配置的記憶體，因此在函數內的形式參數執行完畢時，並不會更動到原本主程式中呼叫的內容變數
  >回傳資料型態 函數名稱(資料型態 參數1, 資料型態 參數2, ...); (function declaration)  
  >...  
  >函數名稱(引數1, 引數2, ...); (function call)

  ##### <span style="color:#e5c07b">2. 傳址呼叫(call by address)</span>
  將實際參數的<span style="color:#e5c07b">位址</span>直接傳遞給所對應的形式參數，也就是配置<span style="color:#e5c07b">指標變數的形式參數</span>來存放傳入的變數位址，待函數執行完畢後，將指標指向實際參數的變數位址，更改變數內容
  >回傳資料型態 函數名稱(資料型態 \*參數1, 資料型態 \*參數2, ...); (function declaration)  
  >...  
  >函數名稱(&引數1, &引數2, ...); (function call)

  ##### <span style="color:#e5c07b">3. 傳參考呼叫(call by reference)</span>
  形式變數不會另外再配置記憶體存放實際參數傳入的位址，而是直接把形式參數作為實際參數的一個<span style="color:#e5c07b">別名</span>
  >回傳資料型態 函數名稱(資料型態 &參數1, 資料型態 &參數2, ...); (function declaration)  
  >...  
  >函數名稱(引數1, 引數2, ...); (function call)

  !FILENAME Example 1
  ```cpp
  void func_cbv(int a, int b);
  void func_cba(int *a, int *b);
  void func_cbr(int &a, int &b);

  int main(){
      int a = 10, b = 41;

      func_cbv(a, b);   // call by value
      func_cba(&a, &b); // call by address
      func_cbr(a, b);   // call by reference
      
      return 0;
  }

  void func_cbv(int a, int b){
    a = 41;
    b = 10;
  }
  void func_cba(int *a, int *b){
    *a = 41;
    *b = 10;
  }
  void func_cbr(int &a, int &b){
    a = 10;
    b = 41;
  }
  ```
  !FILENAME Output 1
  ```
  Line 06: a = 10 , b = 41 , &a = 0x61ff0c , &b = 0x61ff08
  Line 15: a = 10 , b = 41 , &a = 0x61fef0 , &b = 0x61fef4
  Line 08: a = 10 , b = 41 , &a = 0x61ff0c , &b = 0x61ff08

  Line 19: a = 0x61ff0c , b = 0x61ff08 , *a = 10 , *b = 41

  Line 09: a = 41 , b = 10 , &a = 0x61ff0c , &b = 0x61ff08
  Line 23: a = 41 , b = 10 , &a = 0x61ff0c , &b = 0x61ff08
  Line 10: a = 10 , b = 41 , &a = 0x61ff0c , &b = 0x61ff08
  ```

- 由於某些參數只有在特殊情況下才會變動，因此可以採取設定參數預設值的方式，其函數<span style="color:#e5c07b">原型宣告</span>方式如下
  >回傳資料型態 函數名稱(資料型態 參數1, 資料型態 參數2, ..., 資料型態 參數n = 預設值);

  &nbsp;
  >[!TIP]
  >1. 有預設值的參數必須放置在參數列的尾端 
  >2. 不能在函數定義時再次設定參數的預設值

- 陣列名稱儲存的是陣列第一個元素的記憶體位址，因此可以使用<span style="color:#e5c07b">傳址呼叫</span>傳遞陣列給另一個函數，函數原型宣告方式  
  一維陣列：
  >回傳資料型態 函數名稱(資料型態 *陣列名稱, ...);  
  >or  
  >回傳資料型態 函數名稱(資料型態 陣列名稱[陣列大小], ...);

  二維陣列：
  >回傳資料型態 函數名稱(資料型態 陣列名稱[列數][行數], ...);

  函數呼叫方式
  >函數名稱(陣列名稱);

  !FILENAME Example 2
  ```cpp
  void func(int arr[2][3]);

  int main(){
      int arr[2][3] = { {1, 2, 3}, {4, 5, 6} };

      cout << arr <<endl;

      func(arr);

      for(int i = 0; i < 6; i++){
          cout << *(&arr[0][0]+i) << ' ';
      }   

      return 0;
  }
  void func(int arr[2][3]){
      cout << arr <<endl;

      for(int i = 0; i < 2; i++){
          for(int j = 0; j < 3; j++){
              arr[i][j] += 1;
          }
      }
  }
  ```
  !FILENAME Output 2
  ```
  Line 06: 0x61fef4
  Line 17: 0x61fef4
  Line 11: 2 3 4 5 6 7
  ```

- 指標也可做為函數的回傳值，原型宣告方式
  >回傳資料型態 *函數名稱(資料型態 參數1, 資料型態 參數2, ...);

  !FILENAME Example 3
  ```cpp
  char* func(char* str1, char* str2); // call by address

  int main(){
      char str1[100] = {"Hello "};
      char str2[100] = {"World"};

      cout << (int *)str1 << endl;

      char *str3 = func(str1, str2);

      cout << str3 << endl;
      cout << (int *)str3 << endl;

      return 0;
  }

  char* func(char* str1, char* str2){
      int i = 0, j = 0;
      while(*(str1+i) != '\0'){
          i++;
      }
      while(*(str2+j) != '\0'){
          *(str1+i+j) = *(str2+j);
          j++;
      }
      *(str1+i+j) = '\0';

      cout << (int *)str1 << endl;

      return str1;
  }
  ```
  !FILENAME Output 3
  ```
  Line 07: 0x61fea8
  Line 28: 0x61fea8
  Line 11: Hello World
  Line 12: 0x61fea8
  ```