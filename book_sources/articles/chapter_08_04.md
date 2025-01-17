# Typedef, Enum, and Union

##### <span style="color:#e5c07b">1. 型態定義指令(typedef)</span>

- 型態定義指令可將原有的<span style="color:#e5c07b">型態或結構</span>以有意義的新名稱取代，提高程式的可讀性
  >typedef 原型態 新定義型態;

  !FILENAME Example 1
  ```cpp
  typedef int INTEGER;     // INTEGER被定義成int型態
  typedef char STRING[20]; // STRING被定義成長度20的字元陣列
  typedef struct hotel{
			INTEGER room_number;
			STRING hotel_name;
  }HOTEL_INFO;             // HOTEL_INFO被定義成struct hotel型態

  int main(){
			HOTEL_INFO myhotel = {920, "Guitar_hotel"}; // 不必加上struct

			cout << myhotel.room_number << endl;
			cout << myhotel.hotel_name << endl;
			
			return 0;
	}
	```
  !FILENAME Output 1
  ```
  Line 11: 920
  Line 12: Guitar_hotel
  ```

##### <span style="color:#e5c07b">2. 列舉型態指令(enum)</span>

- 列舉型態指令的功能是給予一組常數集合而成的列舉成員，<span style="color:#e5c07b">各常數值不同的命名</span>。若無指定數值，預設將第一個列舉成員設為0，後面列舉成員的常數值則依序遞增
  >(declaration)  
  >enum 列舉型態名稱{  
	>&nbsp;&nbsp;&nbsp;&nbsp;列舉成員1 = 預設值1;  
	>&nbsp;&nbsp;&nbsp;&nbsp;列舉成員2 = 預設值2;  
	>&nbsp;&nbsp;&nbsp;&nbsp;...  
	>};  
	>(definition)    
	>enum 列舉型態名稱 列舉型態變數;

  !FILENAME Example 2
  ```cpp
	enum drink{
			coffee,
			milk,
			tea = 41,
			water,
			juice = 10
  };

	enum drink mydrink;

	mydrink = coffee;
	cout << mydrink << endl;

	mydrink = milk;
	cout << mydrink << endl;

	mydrink = tea;
	cout << mydrink << endl;

	mydrink = water;
	cout << mydrink << endl;

	mydrink = juice;
	cout << mydrink << endl;
  ```
	
  !FILENAME Output 2
  ```
  Line 12: 0
  Line 14: 1
	Line 16: 41
	Line 18: 42
	Line 20: 10
  ```

  

