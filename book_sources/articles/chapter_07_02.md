# Pointer of Functions

- 函數名稱其實也是一個指標變數，指向函數內容所在的記憶體起始位址，因此我們可以宣告一個<span style="color:#e5c07b">指向函數起始位址的函數指標(pointer of function)</span>，並藉由該指標變數來呼叫函數  
  函數指標的宣告方式：
  >回傳資料型態 (*函數指標名稱)(資料型態 參數1, ...); // 括號不可省略

  !FILENAME Example 1
  ```cpp
  int (*ptr)();        // 函數指標ptr無引數，回傳整數值
  int (*ptr)(int);     // 函數指標ptr接受整數引數，回傳整數值
  char* (*ptr)(char*); // 函數指標ptr接受字元指標引數，回傳字元指標
  ```

  將函數指標指向函數的方式：
  >回傳資料型態 (*函數指標名稱)(資料型態 參數1, ...) = 函數名稱; // 宣告時直接指向  
  >or  
  >回傳資料型態 (*函數指標名稱)(資料型態 參數1, ...);  
  >函數指標名稱 = 函數名稱;

  !FILENAME Example 2
  ```cpp
  int add(int a, int b);
  int sub(int a, int b);

  int main(){

      int (*ptr)(int a, int b);

      ptr = add;
      cout << (*ptr)(41, 10) << endl; // 以*取值(*應該可省略)
      ptr = sub;
      cout << (*ptr)(41, 10) << endl;

      return 0;
  }

  int add(int a, int b){
      return (a + b);
  }
  int sub(int a, int b){
      return (a - b);
  }
  ```
  !FILENAME Output 2
  ```
  Line 09: 51
  Line 11: 31
  ``` 

- 可以將函數指標用來作為<span style="color:#e5c07b">另一個函數的參數</span>(參數型函數指標)，此時須將函數指標直接宣告於函數的參數列
  >回傳資料型態 函數名稱(資料型態 參數1, ..., 回傳資料型態 (*函數指標名稱)(資料型態 參數1, ...));

  !FILENAME Example 2
  ```cpp
  int add(int a, int b);
  int sub(int a, int b);

  int main(){

      int (*ptr)(int a, int b);

      ptr = add;
      cout << (*ptr)(41, 10) << endl; // 以*取值(*應該可省略)
      ptr = sub;
      cout << (*ptr)(41, 10) << endl;

      return 0;
  }

  int add(int a, int b){
      return (a + b);
  }
  int sub(int a, int b){
      return (a - b);
  }
  ```
  !FILENAME Output 2
  ```
  Line 09: 51
  Line 11: 31
  ``` 
