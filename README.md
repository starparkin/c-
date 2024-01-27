# c-
在线学习c++语言
# c++

## 第一个c程序

```c++
#include<iostream>
using namespace std;

int main()
{
	cout << "helllo world" << endl;

	system("pause");//请按任意键继续
}
```

## 注释

1. **单行注释**：// 描述信息
2. **多行注释**：/* 描述信息 */

## 变量的使用

```c++
#include<iostream>
using namespace std;

int main()
{
	//变量的使用
	int a = 5;
	cout << "a=" <<a<< endl;

	system("pause");//请按任意键继续
}
```

## 常量

用于记录程序中不可更改的数据

1. **#define** 宏常量：#define 常量名  常量值

+ 通常在文件上定义，表示一个常量

2. **const**修饰的变量：const 数据类型 常量名  =常量值

```c++
#include<iostream>
using namespace std;
#define day 7
int main()
{
	const int month = 12;
	cout << "一周有：" <<day<<month<< endl;
	//变量的值不能更改
}
```

## 标识符命名规则

c++规定给标识符命名时，有一套自己的规则

+ 标识符不能是关键字
+ 标识符只能由字母、数字、下划线组成
+ 第一个字符必须为字母或下划线
+ 标识符中字母区分大小写

## 数据类型

c++规定在创建一个变量或者常量时，必须要指出相应的数据类型，否则无法给变量分配内存

### 整形

c++中能够表示的类型有以下方式，区别在于所占内存空间不同

| 数据类型              | 占用空间 | 取值范围       |
| :-------------------- | -------- | -------------- |
| short（短整型）       | 2字节    | (-32768~32767) |
| int（整形）           | 4字节    | (-2^31~2^31-1) |
| long（长整型）        | 4字节    | (-2^31~2^31-1) |
| long long（长长整形） | 8字节    | (-2^63~2^63-1) |

### sizeof关键字

作用：利用sizeof关键字可以统计数据类型所占内存大小

**语法：sizeof(数据类型/变量)**

```c++
#include<iostream>
using namespace std;

int main()
{
	//整形：short(2) int(4) long(4) long long(8)
	//可以利用sizeof求出数据类型占用内存大小
	//语法：sizeof(数据类型/变量）
	short num1 = 10;
	cout << "short 所占用空间为：" << sizeof(num1) << endl;

	return 0;
}
```

### 实型 （浮点型）

作用：用于表示小数

浮点型变量分为两种：

1. 单精度float
2. 双精度double

两者的区别在于表示的有效数字范围不同

| 数据类型 | 占用空间 | 有效数字范围    |
| -------- | -------- | --------------- |
| float    | 4字节    | 7位有效数字     |
| double   | 8字节    | 15~16位有效数字 |

```c++
#include<iostream>
using namespace std;

int main()
{
	float f1 = 3.14159265f;
	double f2 = 3.1415926;
	cout << "f=" << f1 << endl;
	cout << "f2=" << f2 << endl;
	//默认情况下 输出一个小数 会显示出6位有效数字
    //科学计数法
    float f2=3e2;
}
```

### 字符型

作用：字符型变量用于显示单个字符

语法：`char ch='a';`

> 注意1：在显示字符型变量时，用单引号将字符括起来，不要用双引号
>
> 主要2：单引号内只能有一个字符，不可以是字符串

**字符串变量只占用1个字节**

```c++
#include<iostream>
using namespace std;

int main()
{
	char ch = 'a';
	//字符变量要用单引号
	cout << ch << endl;
	cout << sizeof(ch) << endl;
	//字符型变量对应ASCII编码
	cout << (int)ch << endl;
    //a - 97
    //A - 65 
}
```

### 转义字符

作用：用于表示一些不能显示出来的ASCII字符

| 转义字符 | 含义                           | ASCII码值 |
| -------- | ------------------------------ | --------- |
| \\\      | 代表一个反斜线字符             | 092       |
| \b       | 退格，将当前位置移到前一列     | 008       |
| \n       | 换行，将当前位置移到下一行开头 | 010       |
| \t       | 水平制表（跳到下一个TAB位置）  | 009       |
| \?       | 代表一个问号                   | 063       |

### 字符串型

作用：用于表示一串字符

**两种风格**

1. **c风格字符串**：`char 变量名[ ] = "字符串值"`

```c++
int main()
{
	char str1[] = "hello world";//变量名后要加[]
	cout << str1 << endl;

}
```

> 注意：c风格的字符串要用双引号括起来

2. **c++风格字符串**：`string  变量名  =  "字符串值"`

```c++
#include<iostream>
#include<string>
//用c++类型的字符串要加头文件
using namespace std;

int main()
{
	string ch = "hello world";
	cout << ch << endl;
}
```

### 布尔类型

**作用**：布尔数据类型代表真或假的值

bool类型只有两个值：

+ ture --- 真 (本质是1)
+ false ---假 (本质是0)

**bool类型占一个字节大小**

```c++
#include<iostream>
using namespace std;
int main()
{
	bool flag = true;//表示真
	cout << flag << endl;

	flag = false;//表示假
	cout << flag << endl;

	cout << "占用字节数：" << sizeof(bool) << endl;
}

```

### 数据的输入

作用：用于从键盘获取数据

**关键字：cin**

**语法：`cin >> 变量`**

```c++
int main()
{
	//整形
	int a = 0;
	cin >> a;

	//浮点型
	float f = 3.14f;
	cin >> f;

	//字符型
	char ch = 'a';
	cin >> ch;

	//字符串
	string str = "hello";
	cin >> str;

	//bool类型
	bool flag = false;
	cin >> flag;
}

```

## 运算符

作用：用于执行代码的运算

| 运算符类型 | 作用                                   |
| ---------- | -------------------------------------- |
| 算数运算符 | 用于处理四则运算                       |
| 赋值运算符 | 用于将表达式的值赋给变量               |
| 比较运算符 | 用于表达式的比较，并返回一个真值或假值 |
| 逻辑运算符 | 用于根据表达式的值返回真值或假值       |

### 算数运算符

| 运算符 | 术语    | 实列      | 结果    |
| ------ | ------- | --------- | ------- |
| +      | 正号/加 | +3/10+5   | 3/15    |
| -      | 负号/减 | -3/10-5   | -3/5    |
| *      | 乘      | 10*5      | 50      |
| /      | 除      | 10/5      | 2       |
| %      | 取余    | 10%3      | 1       |
| ++     | 前置    | a=2;b=++a | a=3;b=3 |
| ++     | 后置    | a=2;b=a++ | a=3;b=2 |
| --     | 前置    | a=2;b=--a | a=1;b=1 |
| --     | 后置    | a=2;b=a-- | a=1;b=2 |

```c++
int main()
{
	int a = 10;
	int b = 3;
	cout << a + b << endl;
	cout << a - b << endl;
	cout << a * b << endl;
	cout << a / b << endl;//两个整数相除结果依然是整数

	double d = 0.5;
	double c = 0.25;
	cout << d / c << endl;//运算的结果也可以是小数
}
```

> 前置递增 先让变量变化 然后进行表达式运算
>
> 后置递增 先进行表达式运算 然后让变量变化

### 赋值运算符

作用：用于将表达式的值赋给变量

| 运算符 | 术语   | 实列      | 结果     |
| ------ | ------ | --------- | -------- |
| =      | 赋值   | a=2;b=3;  | a=2;b=3; |
| +=     | 加等于 | a=0;a+=2; | a=2;     |
| -=     | 减等于 | a=5;a-=3; | a=2;     |
| *=     | 乘等于 | a=2;a*=2; | a=4;     |
| /=     | 除等于 | a=4;a/=2; | a=2;     |
| %=     | 模等于 | a=3;a%2;  | a=1;     |

### 比较运算符

作用：用于表达式的比较，返回一个真值或假值

| 运算符 | 术语     | 实列 | 结果 |
| ------ | -------- | ---- | ---- |
| ==     | 等于     | 4==3 | 0    |
| !=     | 不等于   | 4!=3 | 1    |
| <      | 小于     | 4<3  | 1    |
| >      | 大于     | 4>3  | 1    |
| <=     | 小于等于 | 4<=3 | 0    |
| >=     | 大于等于 | 4>=1 | 1    |

### 逻辑运算符

作用：用于根据表达式的返回值返回真值或者假值

| 运算符 | 术语 | 实列   | 结果                                                 |
| ------ | ---- | ------ | ---------------------------------------------------- |
| !      | 非   | !a     | 如果a为假，则!a为真                                  |
| &&     | 与   | a&&b   | 如果a和b都为真，则结果为真，否则为假                 |
| \|\|   | 或   | a\|\|b | 如果a和b有一个为真，则结果为真，两者都为假时结果为假 |

## 程序流程结构

c/c++支持最基本的三种程序运行结构：顺序结构、选择结构、循环结构

+ 顺序结构：程序按照顺序执行，不发生跳转
+ 选择结构：依据条件是否满足，有选择的执行相应功能
+ 循环结构：依据条件是否满足，循环多次执行某一段代码

### if语句

作用：执行满足条件的语句

if语句的三种形式

+ 单行格式if语句：`if(条件){条件满足执行的语句}`
+ 多行格式if语句：`if(条件){条件满足执行语句}else{条件不满足执行的语句}`
+ 多条件的if语句：`if(条件1){条件1满足执行的语句}else if(条件2){条件2满足执行的语句}...else{都不满足执行的条件}`

```c++
if (score > 4)
{
	cout << "确实大于4" << endl;
}

if (score>4)
{
	cout << "大于4" << endl;
}
else
{
	cout << "不大于4" << endl;
}

if (score>4)
{
	cout << "大于4" << endl;
}
else if (score > 10)
{
	cout << "大于10" << endl;
}
else if (score > 15)
{
	cout << "大于15" << endl;
}
else
{
	cout << "小于4" << endl;
}
```

### 三目运算符

作用：通过三目运算符实现简单的判断

语法：`表达式1 ? 表达式2 : 表达式3`

解释：

如果表达式1的值为真，执行表达式2，并且返回表达式2的结果

如果表达式1的值为假，执行表达式3，并且返回表达式3的结果

```c++
int a = 10;
int b = 20;
int c = 0;
c = (a > b ? a : b);
cout << c;
```

### switch语句

作用：执行条件分支语句

语法：

```c++
switch(表达式)
{
    case 结果1:执行语句;break;
    case 结果2:执行语句;break;
    ...
    default:执行语句;break;        
}
//如果语句后面没有加上break就会都会执行
```

### while循环语句

作用：满足循环条件，执行循环语句

语法：`while(循环条件){循环语句}`

```c++
while(num<10)
{
    cout<<num<<endl;
    num++;
}
```

> 在执行循环语句的时候，程序必须提供跳出循环的出口，否则出现死循环

### c++生成随机数

```c++
#include<ctime>//使用随机数时要添加头文件

srand((unsingned int)time(NULL))
int num=rand()%100+1;//生成随机数为1到100
```

### do...while循环语句

作用：满足循环条件，执行循环语句

语法：`do{循环语句}while{循环条件}`

```c++
do
{
    cout<<num<<endl;
    num++;
}
while(num<10);
//与while的区别：先执行语句，再判断条件
//最后要加分号
```

### for循环语句

作用：满足循环条件，执行循环语句

语法：`for(起始表达式 ; 条件表达式 ; 末尾循环体) {循环语句; }`

```c++
for(int i=0;i<10;i++)
{
    cout<<i<<endl;
}
```

### break语句

作用:用于跳出选择结构或者循环结构

break使用的时机：

+ 出现在switch条件语句中，作用是终止case并跳出switch
+ 出现在循环语句中，作用是跳出当前的循环语句
+ 出现在嵌套循环中，跳出最近的内层循环语句

```c++
for (int i = 1; i <= 10; i++) 
{
        cout << "i = " << i << endl;
        if (i == 5) 
        {
            cout << "Breaking the loop at i = 5" << endl;
            break;
        }
}
```



### continue语句

作用：在循环语句中，跳出本次循环中余下尚未执行的语句，继续执行下一次循环

```c++
for (int i = 1; i <= 5; i++) 
{
        if (i == 3) 
        {
            cout << "Skipping i = 3" << endl;
            continue;
        }
        cout << "i = " << i << endl;
}
```



### goto语句

作用：可以无条件跳转语句

语法：`goto 标记;`

```c++
int main() {
    int i = 1;
    
start:
    if (i <= 5) {
        cout << "i = " << i << endl;
        i++;
        goto start;
    }
    
    return 0;
}
```

## 数组

### 一维数组

> 在C++中，一维数组是一组具有相同类型的元素的集合，这些元素按照顺序存储在一块连续的内存空间中。一维数组可以通过下标来访问其中的元素，数组的下标从0开始。

一维数组的相关知识点包括：

1. 声明和初始化：可以通过指定数组的大小和元素类型来声明和初始化数组，例如：int arr[5] = {1, 2, 3, 4, 5};
2. 访问元素：可以使用下标来访问数组中的元素，例如：int x = arr[2];
3. 数组长度：可以使用sizeof操作符或者通过数组大小来获取数组的长度，例如：int len = sizeof(arr) / sizeof(arr[0]);
4. 数组作为函数参数：可以将数组作为函数参数传递，例如：void printArray(int arr[], int size);
5. 数组的遍历：可以使用循环结构来遍历数组中的元素，例如：for (int i = 0; i < 5; i++) { cout << arr[i] << " "; }
6. 动态数组：可以使用new和delete关键字来创建和销毁动态数组，例如：int* arr = new int[5]; delete[] arr;

当声明一个一维数组时，可以使用以下语法：

```cpp
// 声明一个包含5个整数的数组，并初始化
int arr1[5] = {1, 2, 3, 4, 5};

// 声明一个包含3个双精度浮点数的数组，并初始化
double arr2[3] = {3.14, 2.718, 1.414};

// 声明一个包含4个字符的数组，并初始化
char arr3[4] = {'a', 'b', 'c', 'd'};
```

访问数组元素的例子如下：

```cpp
int x = arr1[2]; // 获取arr1数组中下标为2的元素值
```

数组作为函数参数的例子：

```cpp
void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
}

// 调用函数并传递数组作为参数
int arr[] = {1, 2, 3, 4, 5};
printArray(arr, 5);
```

动态数组的例子：

```cpp
int* dynamicArr = new int[10]; // 创建一个包含10个整数的动态数组
dynamicArr[0] = 100; // 给动态数组赋值
delete[] dynamicArr; // 销毁动态数组，释放内存
```

## 函数

在C++中，函数是一组执行特定任务的语句块，可以通过函数来组织代码、提高代码的可读性和可维护性。

当谈到C++中的函数，以下是一些重要的知识点：

1. 函数声明和定义：在C++中，函数需要先声明后定义。函数声明包括函数的返回类型、函数名和参数列表，而函数定义包括函数的具体实现。

   ```cpp
   // 函数声明
   int add(int a, int b);
   
   // 函数定义
   int add(int a, int b) {
       return a + b;
   }
   ```

2. 函数参数：函数可以接受零个或多个参数，参数可以是各种类型，包括基本类型、数组、结构体、类等。

   ```cpp
   void printMessage(string message);
   void processArray(int arr[], int size);
   ```

3. 函数返回值：函数可以返回一个值，返回值的类型由函数声明时指定。

   ```cpp
   int add(int a, int b) {
       return a + b;
   }
   ```

4. 函数重载：C++允许函数名相同但参数列表不同的多个函数共存，这被称为函数重载。

   ```cpp
   int add(int a, int b);
   double add(double a, double b);
   ```

5. 函数调用：函数可以在程序中被调用执行。

   ```cpp
   int result = add(3, 5);
   ```

6. 函数参数传递：C++中的函数参数传递可以是值传递、引用传递、指针传递等方式，不同的传递方式对应不同的参数修改方式和性能特点。

7. 默认参数：C++允许在函数定义时为参数指定默认值，这样在调用函数时可以不传递对应的参数。

8. 内联函数：使用关键字inline可以声明内联函数，这样可以减少函数调用的开销，提高程序的运行效率。

## 指针

指针的作用：可以通过指针间接访问内存

+ 内存编号是从0开始记录的，一般用十六进制数字表示
+ 可以利用指针变量保存地址

指针变量的定义语法：`数据类型 * 变量名;`

```c++
//定义指针
int a = 10;
//定义指针的语法：数据类型 * 指针变量;
int* p;
//记录变量a的地址
p = &a;
//*p=a
```

**指针所占空间大小**

64位系统基本都是8位，32位系统基本都是4位

```c++
int a = 10;
int* p = &a;
cout << sizeof(p);
//8
```

### 空指针和野指针

**空指针**：指针变量指向内存中编号为0的空间

用途：初始化指针变量

注意：空指针的内存是不可以访问的

```c++
int* p = NULL;
```

野指针：指针变量指向非法的内存空间

```c++
int* p = (int*)0x1100;
```

语法没有错误，但是不能访问内存空间

**空指针和野指针都不是我们申请的空间，因此不要访问**

### const 修饰指针

const修饰指针有三种情况：

1. const修饰指针 ---常量指针
2. const修饰常量 ---指针常量
3. const即修饰指针，又修饰常量

**常量指针：**

```c++
int a = 10;
int b = 10;
const int * p = &a;
//常量指针特点：指针的指向可以修改，但是指针指向的值不可修改
//*p=20;是错误的，指针指向的值不可修改
p = &b;
//指针指向可以修改
```

**指针常量：**

```c++
int * const p = &a;
//指针常量的特点：指针的指向不可改，指针指向的值可以改
//*p=&b;是错误的
*p=20;
//指针指向的值可以改
```

**const即修饰指针，又修饰常量**

```c++
const int * const p = &a;
//指针指向和指针的值都不能改
```

### 指针和数组

作用：利用指针访问数组中的元素

```c++
int arr[10] = { 1,2,3,4,5,6,7,8,9,10 };
int* p = arr;
//arr就是数组首地址
cout << *p << endl;

p++;
//指针偏移4个字节
cout << *p;
```

### 指针和函数

作用：利用指针作为函数的参数，可以修改实参的值

```c++
#include<iostream>
using namespace std;

void swap(int* p1, int* p2)
{
	int temp = *p1;
	*p1 = *p2;
	*p2 = temp;
}


int main()
{
	int a = 10;
	int b = 10;
	swap(&a, &b);
	cout << a << endl;
	cout << b << endl;
	//最后的结果为a=10，b=10
	//因为调用函数后有参无反，没有返回值就没有改变原来的值
}
```

## 结构体

结构体属于用户自定义的数据类型，允许用户存储不同的数据类型

### 结构体定义和使用

语法：`struct  结构体名  { 结构体成员名 }`

通过结构体创建变量的方式有三种：

+ struct  结构体名  变量名
+ struct  结构体名  变量名 = {成员1值，成员2值...}
+ 定义结构体时顺便创建变量

```c++
#include<iostream>
using namespace std;

struct student
{
	int height=0;
	char sex=0;
	int goal=0;
};

int main()
{
	struct student s1;
	s1.goal = 80;
	s1.height = 180;
	cout << s1.goal << " " << s1.height << endl;

}
```

### 结构体数组

语法：`struct  结构体名  数组名[元素个数]  =  { {} , {} ,... {} }`

```c++
#include<iostream>
#include<string>
using namespace std;
struct student
{
	string name;
	int age;
	int score;
};

int main()
{
	struct student remenber[3] = { {"san",18,100} ,{"lisa",14,89},{"lise",12,79} };
	cout << remenber[1].name << endl;
}
```

### 结构体指针

作用：通过指针访问结构体中的成员

+ 利用操作符 `->` 可以通过结构体指针访问结构体属性

```c++
struct student remenber={"san",18,100};
//通过指针指向结构体变量
struct student * p = &remenber;
//通过指针访问结构体变量中的数据
cout << p->name << " " << p->age << endl;
```

### 结构体嵌套结构体

作用：结构体中的成员可以是另一个结构体

```c++
struct student
{
	string name;
	int age;
	int score;
};
struct teacher
{
	string name;
	int id;
	struct student stu;
};

int main()
{
	//创建一个老师
	teacher t;
	t.name = "laow";
	t.id = 222;
	t.stu.name = "xiaoming";
	t.stu.score = 88;
	cout << t.name << " " << t.id << endl;
	cout << t.stu.name << " " << t.stu.score << endl;
}

```

### 结构体做函数参数

作用：将结构体作为参数向函数中传递

传递方式有两种：

+ 值传递
+ 地址传递

```c++
void student1(struct student s)
{
	cout << s.name << " " << s.age << " " << s.score << endl;
}
//值传递后，在函数中改变形参的数值，不会影响实参的值
void student2(struct student *p)
{
	cout << p->name << " " << p->age << endl;
}
//地址传递后，在函数体中改变参数的值时会影响实参的值
//使用地址传递，可以减少内存空间的使用，而且不会复制新的副本出来
s.name = "xioaming";
s.age = 18;
s.score = 88;
student1(s);
student2(&s);
//接收的是地址，传入的也要是地址
```

### 结构体中 const使用场景

```c++
void student2(const student * p)//加const防止函数中的误操作，这样就不会改变原来的参数值
{
	cout << p->name << " " << p->age << endl;
}
```

