# Variable Type Modifiers

##### <span style="color:#e5c07b">1. 自動變數</span>
- 必須宣告在<span style="color:#e5c07b">函數區塊內</span>，是系統預設的變數型態，在程式執行到區域範圍時才會被建立，當程式離開此範圍後所占用的記憶體空間會被釋放
  >auto 資料型態 變數名稱;

##### <span style="color:#e5c07b">2. 靜態區域變數</span>
- 宣告在函數區塊內，當函數執行完畢後，<span style="color:#e5c07b">記憶體位址不會被清除</span>，若再次呼叫該函數時，<span style="color:#e5c07b">會將放在記憶體中的值取出</span>，而不是定義的初值。若無設定初始值，系統會設定為0
  >static 資料型態 變數名稱;

##### <span style="color:#e5c07b">3. 外部變數</span>
- 外部變數是指宣告在函數區塊外的變數，也就是全域變數，會占用固定的記憶體空間。若無設定初始值，系統會設定為0。定義後以下所有的函數都可使用該變數，待程式執行結束後才將記憶體釋放。  
  extern修飾詞的功能可將宣告在函數區塊後方的外部變數<span style="color:#e5c07b">引用到函數內使用</span>
  >extern 資料型態 變數名稱;

##### <span style="color:#e5c07b">4. 靜態外部變數</span>
- 將靜態變數宣告在函數區塊之外即為靜態外部變數，與外部變數不同的是靜態外部變數只限於在同一個程式檔案使用

##### <span style="color:#e5c07b">5. 暫存器變數</span>
- 使用CPU的暫存器來儲存變數，加快變數存取的效率
  >register 資料型態 變數名稱;

