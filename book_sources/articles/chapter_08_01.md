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
  >or  
  >結構型態名稱 結構變數;

- 結構資料的存取
  >結構變數.結構成員名稱;