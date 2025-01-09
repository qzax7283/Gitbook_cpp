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
  >或  
  >函數名稱(void);

  若函數有回傳值
  >變數 = 函數名稱(引數1, 引數2, ...);

- 函數參數的種類分為以下兩種：  
&nbsp;1. <span style="color:#e5c07b">形式參數(Formal Parameter)</span>：在函數定義標頭中所宣告的參數  
&nbsp;2. <span style="color:#e5c07b">實際參數(Actual Parameter)</span>：實際呼叫函數時所提供的參數  

- 對於傳遞參數的方式，可以根據傳遞和接收的是參數數值或參數位址分為三種  
  #### 傳值呼叫(call by value)


