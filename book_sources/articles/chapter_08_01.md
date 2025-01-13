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
  };
  int main(){

      struct circle c1;
      struct circle *ptr = &c1;

      c1.r = 3;
      c1.area = 3.14 * c1.r * c1.r;

      cout << ptr -> r << endl;
      cout << (*ptr).r << endl;

      cout << ptr -> area << endl;
      cout << (*ptr).area << endl;

      return 0;
  }
  ```
  !FILENAME Output 1
  ```
  Line 13: 3
  Line 14: 3
  Line 16: 28.26
  Line 17: 28.26
  ```