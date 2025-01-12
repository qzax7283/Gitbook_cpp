# Function Overloading

- 同一個函數名稱可以用來定義<span style="color:#e5c07b">多個函數主體</span>，以參數來判斷應執行哪一個函數功能，因此函數多載必須遵循以下兩個原則來定義函數  
&nbsp;1. 函數名稱必須<span style="color:#e5c07b">相同</span>
&nbsp;2. 各多載函數間的參數列(arguments list)<span style="color:#e5c07b">型態與個數不能完全相同</span>

  !FILENAME Example 1
  ```cpp
  int func(int a, int b);
  int func(int a, int b, int c);
  double func(double a);

  int main(){

      cout << func(10, 41) << endl;
      cout << func(10, 37, 41) << endl;
      cout << func(2.5) << endl;

      return 0;
  }

  int func(int a, int b){
      return (a * b);
  }
  int func(int a, int b, int c){
      return (a * b * c);
  }
  double func(double a){
      return (3.14 * a * a);
  }
  ```
  !FILENAME Output 1
  ```
  Line 07: 410
  Line 08: 15170
  Line 09: 19.625
  ```

