# Nested Structure

- 巢狀結構指的是在一個結構中宣告建立另一個結構，宣告方式有兩種，具體使用方法如下
  
  !FILENAME Example 1
  ```cpp
  struct student{
        const char name[15];
        int id;
        double gpa;
  }; // 宣告在巢狀結構外面

  struct apartment{
      const char abbr[15];
      struct student stu[2];
      struct{
          const char name[15];
          int id;
      }prof[2]; // 宣告在巢狀結構內部，省略了結構的型態名稱
  };

  struct apartment a1 = {"EE", "Ashley", 1056, 4.21, "Bob", 1788, 4.01, "Celine", 113, "David", 110};

  cout << a1.abbr << endl;
  cout << a1.stu[1].gpa << endl;
  cout << a1.prof[0].name << endl;
  ```
  !FILENAME Output 1
  ```
  Line 18: EE
  Line 19: 4.01
  Line 20: Celine
  ```

