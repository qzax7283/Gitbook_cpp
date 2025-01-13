# Structure

- 結構可以集合不同的資料型態，形成一種新的資料型態，因此結構宣告是在<span style="color:#e5c07b">建立一種新型態</span>，宣告後才能建立<span style="color:#e5c07b">結構變數</span>來加以利用  
- 結構型態宣告方式
  >struct 結構型態名稱{  
  >&nbsp;&nbsp;&nbsp;&nbsp;資料型態 結構成員1;  
  >&nbsp;&nbsp;&nbsp;&nbsp;資料型態 結構成員2;  
  >&nbsp;&nbsp;&nbsp;&nbsp;...  
  >};

- 結構變數定義方式
  >struct 結構型態名稱{  
  >&nbsp;&nbsp;&nbsp;&nbsp;資料型態 結構成員1;  
  >&nbsp;&nbsp;&nbsp;&nbsp;資料型態 結構成員2;  
  >&nbsp;&nbsp;&nbsp;&nbsp;...  
  >}結構變數; // 宣告後直接定義  
  
  或
  >struct 結構型態名稱 結構變數;

- 結構資料的存取
  >結構變數.結構成員名稱;

- 若以結構為資料型態宣告的指標變數稱為<span style="color:#e5c07b">結構指標</span>
  >struct 結構型態名稱 *結構指標名稱;

- 與一般的指標變數相同，必須先指定結構變數的位址給指標，才能間接存取其指定結構變數的成員
  >結構指標名稱 = &結構變數;

- 結構指標的資料存取方法
  >結構指標名稱 -> 結構成員名稱;

  或
  >(*結構指標名稱).結構成員名稱;

  !FILENAME Example 1
  ```cpp
  struct circle{
      int r;
      double area;
      char name[10];
  };
  int main(){

      struct circle c1 = {0, 0, "circle_1"}; // 可指定初始值
      struct circle *ptr = &c1;

      c1.r = 3;
      c1.area = 3.14 * c1.r * c1.r;

      cout << c1.name << endl;

      cout << ptr -> r << endl;
      cout << (*ptr).r << endl;

      cout << ptr -> area << endl;
      cout << (*ptr).area << endl;

      return 0;
  }
  ```
  !FILENAME Output 1
  ```
  Line 14: circle_1
  Line 16: 3
  Line 17: 3
  Line 19: 28.26
  Line 20: 28.26
  ```

- 若要在函數中傳遞結構型態，必須在<span style="color:#e5c07b">全域範圍</span>內事先宣告。而函數中結構資料的傳遞有三種方式
  ##### <span style="color:#e5c07b">1. 結構傳值呼叫</span>
  將整個結構變數<span style="color:#e5c07b">複製</span>到函數裡，若在函數中更改了傳來的參數值，則main中結構變數的值不會更改
  >回傳資料型態 函數名稱(struct 結構型態名稱 結構變數); (function declaration)  
  >...  
  >函數名稱(結構變數); (function call)

  ##### <span style="color:#e5c07b">2. 結構傳址呼叫</span>
  將結構變數的位址傳給函數，在函數內使用<span style="color:#e5c07b">結構指標</span>來存取資料，若在函數中更改了傳來的參數值，則main中結構變數的值也會同步更改
  >回傳資料型態 函數名稱(struct 結構型態名稱 *結構變數); (function declaration)  
  >...  
  >函數名稱(&結構變數); (function call)

  ##### <span style="color:#e5c07b">3. 結構傳參考呼叫</span>
  把傳遞到函數中的結構變數作為main中結構變數的一個<span style="color:#e5c07b">別名</span>，若在函數中更改了傳來的參數值，則main中結構變數的值也會同步更改
  >回傳資料型態 函數名稱(struct 結構型態名稱 &結構變數); (function declaration)  
  >...  
  >函數名稱(結構變數); (function call)

  !FILENAME Example 2
  ```cpp
  struct circle{
      const char name[10];
      int r;
      double area;
  };

  void func_cbv(struct circle c);
  void func_cba(struct circle *c);
  void func_cbr(struct circle &c);

  int main(){

      struct circle c[3] = { {"circle_1", 3, 0.0},
                            {"circle_2", 3, 0.0},
                            {"circle_3", 3, 0.0} };

      func_cbv(c[0]);
      func_cba(&c[1]);
      func_cbr(c[2]);

      cout << c[0].area << endl;
      cout << c[1].area << endl;
      cout << c[2].area << endl;

      return 0;
  }
  void func_cbv(struct circle c){
      c.area = 3.14 * c.r * c.r;
  }
  void func_cba(struct circle *c){
      (*c).area = 3.14 * (*c).r * (*c).r;
  }
  void func_cbr(struct circle &c){
      c.area = 3.14 * c.r * c.r;
  }
  ```
  !FILENAME Output 2
  ```
  Line 20: 0
  Line 21: 28.26
  Line 22: 28.26
  ```