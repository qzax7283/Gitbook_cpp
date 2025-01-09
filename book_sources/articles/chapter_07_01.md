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
  >回傳資料型態 函數名稱(資料型態 *參數1, 資料型態 *參數2, ...); (function declaration)  
  >...  
  >函數名稱(&引數1, &引數2, ...); (function call)

  ##### <span style="color:#e5c07b">3. 傳參考呼叫(call by reference)</span>
  形式變數不會另外再配置記憶體存放實際參數傳入的位址，而是直接把形式參數作為實際參數的一個別名
  >回傳資料型態 函數名稱(資料型態 &參數1, 資料型態 &參數2, ...); (function declaration)  
  >...  
  >函數名稱(引數1, 引數2, ...); (function call)

