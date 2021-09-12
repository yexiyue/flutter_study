

# 							flutter学习

## 一.dart学习

### 1.Dart 变量：

  dart是一个强大的脚本类语言，可以不预先定义变量类型 ，自动会类型推倒

  dart中定义变量可以通过var关键字可以通过类型来申明变量

  如：

```dart

    var str='this is var';

    String str='this is var';

    int str=123;

 // 注意： var 后就不要写类型 ，  写了类型 不要var   两者都写   var  a int  = 5;  报错
```



### 2.Dart 常量：   final 和 const修饰符  

**const**值不变 一开始就得赋值
**final** 可以开始不赋值 只能赋一次 ; 而final不仅有const的编译时常量的特性，最重要的它是运行时常量，并且final是惰性初始化，即在运行时第一次使用前才初始化
永远不改量的量，请使用final或const修饰它，而不是使用var或其他变量类型。


```dart
final name = 'Bob'; // Without a type annotation
final String nickname = 'Bobby';
final time=new Date.now();//只有final可以这么用 ，const不行

const bar = 1000000; // Unit of pressure (dynes/cm2)
const double atm = 1.01325 * bar; // Standard atmosphere
```



### 3.Dart的命名规则：

1.   变量名称必须由数字、字母、下划线和美元符($)组成。

2.   注意：标识符开头不能是数字

3.   标识符不能是保留字和关键字。   

4.   变量的名字是区分大小写的如: age和Age是不同的变量。在实际的运用中,也建议,不要用一个单词大小写区分两个变量。

5.   标识符(变量名称)一定要见名思意 ：变量名称建议用名词，方法名称建议用动词  



### 4.Dart中支持以下数据类型：

```dart
  常用数据类型：
      Numbers（数值）:
          int
          double
      Strings（字符串）
          String  //三个单双引号可以定义多行
      Booleans(布尔)
          bool
      List（数组）
          在Dart中，数组是列表对象，所以大多数人只是称它们为列表
              //创建固定长度的集合
              var list=List<String>.filled(2,"张三")
      Maps（字典）
          通常来说，Map 是一个键值对相关的对象。 键和值可以是任何类型的对象。每个 键 只出现一次， 而一个值则可以出现多次

```

 项目中用不到的数据类型 （用不到）：
      Runes 

```dart
 //Rune是UTF-32编码的字符串。它可以通过文字转换成符号表情或者代表特定的文字。
main() {
      var clapping = '\u{1f44f}';
      print(clapping);
      print(clapping.codeUnits);
      print(clapping.runes.toList());
    
      Runes input = new Runes(
          '\u2665  \u{1f605}  \u{1f60e}  \u{1f47b}  \u{1f596}  \u{1f44d}');
      print(new String.fromCharCodes(input));
    }
```


​        

  Symbols
    Symbol对象表示在Dart程序中声明的运算符或标识符。您可能永远不需要使用符号，但它们对于按名称引用标识符的API非常有用，因为缩小会更改标识符名称而不会更改标识符符号。要获取标识符的符号，请使用符号文字，它只是＃后跟标识符： 在 Dart 中符号用 # 开头来表示，入门阶段不需要了解这东西，可能永远也用不上。



### 5.运算符

```dart
1、Dart运算符：

    算术运算符

      +    -    *    /     ~/ (取整)     %（取余）
      
    关系运算符

      ==    ！=   >    <    >=    <=

    逻辑运算符

        !  &&   ||

    赋值运算符

     基础赋值运算符   =   ??=
     复合赋值运算符   +=  -=  *=   /=   %=  ~/=


    条件表达式 

        if  else   switch case 

        三目运算符

        ??运算符：空合并运算符



2、类型转换

    1、Number与String类型之间的转换
    main() {
      var mynum = '123';
      var a = int.parse(mynum);
      var b = double.parse(mynum);
      print(mynum);
    }

    2、其他类型转换成Booleans类型

```

### 6.List

List里面常用的属性和方法：

```dart
    常用属性：
        length          //长度
        reversed        //翻转
        isEmpty        // 是否为空
        isNotEmpty     // 是否不为空
    常用方法：  
        add         //增加
        addAll      //拼接数组
        indexOf     //查找  传入具体值
        remove      //删除  传入具体值
        removeAt    //删除  传入索引值
        fillRange   //修改   
        insert(index,value);           // 指定位置插入    
        insertAll(index,list)           //指定位置插入List
        toList()    //其他类型转换成List  
        join()      //List转换成字符串
        split()     //字符串转化成List
        forEach   
        map
        where
        any
        every
```



### 7.Set

```dart
//Set 

//用它最主要的功能就是去除数组重复内容

//Set是没有顺序且不能重复的集合，所以不能通过索引去获取值

void main(){

  List myList=['香蕉','苹果','西瓜','香蕉','苹果','香蕉','苹果'];

  var s=new Set();

  s.addAll(myList);

  print(s);

  print(s.toList());

}
```

### 8.Map

```dart
 映射(Maps)是无序的键值对：

    常用属性：
        keys            //获取所有的key值
        values          //获取所有的value值
        isEmpty         //是否为空
        isNotEmpty      //是否不为空
    常用方法:
        remove(key)     //删除指定key的数据
        addAll({...})   //合并映射  给映射内增加属性
        containsValue   //查看映射内的值  返回true/false
        forEach //遍历  
             myList.forEach((value){
      		     print("$value");
      		 });
        map //对数据进行处理
            List myList=[1,3,4];      
      		 var newList=myList.map((value){
      		     return value*2;
      		 });
      		 print(newList.toList());
        where //返回符合条件的新数组
            List myList=[1,3,4,5,7,8,9];

      		 var newList=myList.where((value){
      		     return value>5;
      		 });
      		 print(newList.toList());
        any  //有一个满足就返回true
            List myList=[1,3,4,5,7,8,9];

      		 var f=myList.any((value){   //只要集合里面有满足条件的就返回true
	
      		     return value>5;
      		 });
      		 print(f);
        every //全部满足才返回true
            List myList=[1,3,4,5,7,8,9];

      		 var f=myList.every((value){   //每一个都满足条件返回true  否则返回false

      		    return value>5;
      		 });
     		 print(f);
```

### 9.方法

```dart
内置方法/函数：

      print();

  自定义方法：
      自定义方法的基本格式：

      返回类型  方法名称（参数1，参数2,...）{
        方法体
        return 返回值;
      }
```



```dart
//3、定义一个带可选参数的方法 ，最新的dart定义可选参数需要指定类型默认值

   String printUserInfo(String username,[int age=0]){  //行参
     if(age!=0){
      return "姓名:$username---年龄:$age";
     }
     return "姓名:$username---年龄保密";
   }
   print(printUserInfo('张三',21)); //实参
   print(printUserInfo('张三'));

//4、定义一个带默认参数的方法
   String printUserInfo(String username,[String sex='男',int age=0]){  //行参
     if(age!=0){
       return "姓名:$username---性别:$sex--年龄:$age";
     }
     return "姓名:$username---性别:$sex--年龄保密";
   }
   print(printUserInfo('张三'));
   print(printUserInfo('小李','女'));
   print(printUserInfo('小李','女',30));

//5、定义一个命名参数的方法，最新的dart定义命名参数需要指定类型默认值

   String printUserInfo(String username, {int age = 0, String sex = '男'}) {//行参    
     if (age != 0) {
       return "姓名:$username---性别:$sex--年龄:$age";
     }
     return "姓名:$username---性别:$sex--年龄保密";
   }
   print(printUserInfo('张三', age: 20, sex: '未知'));

```



```dart
//注意和方法的区别: 箭头函数内只能写一条语句，并且语句后面没有分号(;)
   list.forEach((value)=>{
     print(value)
   });
```



```dart
//匿名方法

   var printNum=(){
     print(123);
   };
   printNum();

   var printNum=(int n){
     print(n+2);
   };
   printNum(12);

//自执行方法

   ((int n){
     print(n);
     print('我是自执行方法');
   })(12);

//方法的递归
   var sum = 1;
   fn(int n) {
     sum *= n;
     if (n == 1) {
       return;
     }
     fn(n - 1);
   }

   fn(5);
   print(sum);
```



```dart
/*
闭包：

    1、全局变量特点:    全局变量常驻内存、全局变量污染全局
    2、局部变量的特点：  不常驻内存会被垃圾机制回收、不会污染全局  


  /*  想实现的功能：

        1.常驻内存        
        2.不污染全局   

          产生了闭包,闭包可以解决这个问题.....  

          闭包: 函数嵌套函数, 内部函数会调用外部函数的变量或参数, 变量或参数不会被系统回收(不会释放内存)
  
	        闭包的写法： 函数嵌套函数，并return 里面的函数，这样就形成了闭包。

    */  
*/
//闭包

  fn() {
    var a = 123; /*不会污染全局   常驻内存*/
    return () {
      a++;
      print(a);
    };
  }

  var b = fn();
  b();
  b();
  b();
}
```

### 10.面向对象

面向对象编程(OOP)的三个基本特征是：**封装、继承、多态**      

​      **封装**：封装是对象和类概念的主要特性。封装，把客观事物封装成抽象的类，并且把自己的部分属性和方法提供给其他对象调用, 而一部分属性和方法则隐藏。
​           	
​      **继承**：面向对象编程 (OOP) 语言的一个主要功能就是“继承”。继承是指这样一种能力：它可以使用现有类的功能，并在无需重新编写原来的类的情况下对这些功能进行扩展。
​            	
​      **多态**：允许将子类类型的指针赋值给父类类型的指针, 同一个函数调用会有不同的执行效果 。


Dart所有的东西都是对象，所有的对象都继承自Object类。

Dart是一门使用类和单继承的面向对象语言，所有的对象都是类的实例，并且所有的类都是Object的子类

一个类通常由属性和方法组成。

#### 1.类

```dart
/*

Dart是一门使用类和单继承的面向对象语言，所有的对象都是类的实例，并且所有的类都是Object的子类

*/

class Person{
  String name="张三";
  int age=23;
  void getInfo(){
      // print("$name----$age");
      print("${this.name}----${this.age}");
  }
  void setInfo(int age){
    this.age=age;
  }

}
void main(){

  //实例化

  // var p1=new Person();
  // print(p1.name);
  // p1.getInfo();

  Person p1=new Person();
  // print(p1.name);

  p1.setInfo(28);
  p1.getInfo();
}
```

#### 2.构造函数

```dart
//最新版本的dart中需要初始化不可为null的实例字段，如果不初始化的话需要在属性前面加上late
 class Person{
  late String name;
   late int age; 
   //默认构造函数
   Person(String name,int age){
       this.name=name;
       this.age=age;
   }
   void printInfo(){   
     print("${this.name}----${this.age}");
   }
 }

//最新版本的dart中需要初始化不可为null的实例字段，如果不初始化的话需要在属性前面加上late
class Person{
  late String name;
  late int age; 
  //默认构造函数的简写
  Person(this.name,this.age);
  void printInfo(){   
    print("${this.name}----${this.age}");
  }
}
```

#### 3.命名构造函数

```dart
dart里面构造函数可以写多个

注意：最新版本的dart中需要初始化不可为null的实例字段，如果不初始化的话需要在属性前面加上late
class Person {
  late String name;
  late int age;
  //默认构造函数的简写
  Person(this.name, this.age);
  //命名构造函数
  Person.now() {
    print('我是命名构造函数');
  }

  Person.setInfo(String name, int age) {
    this.name = name;
    this.age = age;
  }

  void printInfo() {
    print("${this.name}----${this.age}");
  }
}
```

#### 4.初始化实例变量

```dart
// Dart中我们也可以在构造函数体运行之前初始化实例变量

class Rect{
  int height;
  int width;
  //初始化实例变量
  Rect():height=2,width=10{
    print("${this.height}---${this.width}");
  }
  getArea(){
    return this.height*this.width;
  } 
}
```

#### 5.getter,setter

```dart
class Rect{
  late num height;
  late num width;   
  Rect(this.height,this.width);
  //getter
  get area{
    return this.height*this.width;
  }
  //setter
  set areaHeight(value){
    this.height=value;
  }
}

void main(){
  Rect r=new Rect(10,4);
  // print("面积:${r.area()}");   
  r.areaHeight=6;

  print(r.area);

}
```

#### 6.私有属性

```dart
/*
Dart和其他面向对象语言不一样，Data中没有 public  private protected这些访问修饰符合

但是我们可以使用_把一个属性或者方法定义成私有。

*/

import 'lib/Animal.dart';

void main(){
 
 Animal a=new Animal('小狗', 3);

 print(a.getName());

 a.execRun();   //间接的调用私有方法
 

}
```

#### 7.static

```dart
/*
Dart中的静态成员:

  1、使用static 关键字来实现类级别的变量和函数

  2、静态方法不能访问非静态成员，非静态方法可以访问静态成员

*/
class Person {
  static String name = '张三';
  int age=20;  
  static void show() {
    print(name);
  }
  void printInfo(){  /*非静态方法可以访问静态成员以及非静态成员*/
      // print(name);  //访问静态属性
      // print(this.age);  //访问非静态属性
      show();   //调用静态方法
  }
  static void printUserInfo(){//静态方法
        print(name);   //静态属性
        show();        //静态方法

        //print(this.age);     //静态方法没法访问非静态的属性
        // this.printInfo();   //静态方法没法访问非静态的方法
        // printInfo();

  }

}
```

#### 8.Dart中的对象操作符

```dart
/*
Dart中的对象操作符:

    ?     条件运算符 （了解）  已被最新dart废弃       
    as    类型转换
    is    类型判断
    ..    级联操作 （连缀）  (记住)
*/
void main(){
    Person p1 = new Person('张三1', 20);
  	p1.printInfo();
  	p1
    ..name = "李四"
    ..age = 30
    ..printInfo();
}
```

#### 9.继承

```dart
/*

面向对象的三大特性：封装 、继承、多态


Dart中的类的继承：  
    1、子类使用extends关键词来继承父类
    2、子类会继承父类里面可见的属性和方法 但是不会继承构造函数
    3、子类能复写父类的方法 getter和setter

*/
class Person {
  String name='张三';
  num age=20; 
  void printInfo() {
    print("${this.name}---${this.age}");  
  } 
}
class Web extends Person{

}

main(){   

  Web w=new Web();
  print(w.name);
  w.printInfo();
 
}
```

#### 10.super关键字，覆写父类的方法，自类调用父类的方法

```dart
class Person {
  String name;
  num age; 
  Person(this.name,this.age);
  void printInfo() {
    print("${this.name}---${this.age}");  
  }
  work(){
    print("${this.name}在工作...");
  }
}

class Web extends Person{
  //super相当于父类
  Web(String name, num age) : super(name, age);

  run(){
    print('run');
    super.work();  //自类调用父类的方法
  }
  //覆写父类的方法
  @override       //可以写也可以不写  建议在覆写父类方法的时候加上 @override 
  void printInfo(){
     print("姓名：${this.name}---年龄：${this.age}"); 
  }
  

}
```

#### 11.抽象类

```dart
/*
Dart中抽象类: Dart抽象类主要用于定义标准，子类可以继承抽象类，也可以实现抽象类接口。


  1、抽象类通过abstract 关键字来定义

  2、Dart中的抽象方法不能用abstract声明，Dart中没有方法体的方法我们称为抽象方法。

  3、如果子类继承抽象类必须得实现里面的抽象方法

  4、如果把抽象类当做接口实现的话必须得实现抽象类里面定义的所有属性和方法。

  5、抽象类不能被实例化，只有继承它的子类可以

extends抽象类 和 implements的区别：

  1、如果要复用抽象类里面的方法，并且要用抽象方法约束自类的话我们就用extends继承抽象类

  2、如果只是把抽象类当做标准的话我们就用implements实现抽象类



案例：定义一个Animal 类要求它的子类必须包含eat方法

*/

abstract class Animal{
  eat();   //抽象方法
  run();  //抽象方法  
  printInfo(){
    print('我是一个抽象类里面的普通方法');
  }
}

class Dog extends Animal{
  @override
  eat() {
     print('小狗在吃骨头');
  }

  @override
  run() {
    // TODO: implement run
    print('小狗在跑');
  }  
}
class Cat extends Animal{
  @override
  eat() {
    // TODO: implement eat
    print('小猫在吃老鼠');
  }

  @override
  run() {
    // TODO: implement run
    print('小猫在跑');
  }

}

main(){

  Dog d=new Dog();
  d.eat();
  d.printInfo();

   Cat c=new Cat();
  c.eat();

  c.printInfo();


  // Animal a=new Animal();   //抽象类没法直接被实例化

}
```

#### 12.多态

Datr中的多态：
    允许将子类类型的指针赋值给父类类型的指针, 同一个函数调用会有不同的执行效果 。

​    子类的实例赋值给父类的引用。
  	
​    **多态就是父类定义一个方法不去实现，让继承他的子类去实现，每个子类有不同的表现。**



#### 13.接口

```dart
/*
和Java一样，dart也有接口，但是和Java还是有区别的。

  首先，dart的接口没有interface关键字定义接口，而是普通类或抽象类都可以作为接口被实现。

  同样使用implements关键字进行实现。

  但是dart的接口有点奇怪，如果实现的类是普通类，会将普通类和抽象中的属性的方法全部需要覆写一遍。
  
  而因为抽象类可以定义抽象方法，普通类不可以，所以一般如果要实现像Java接口那样的方式，一般会使用抽象类。

  建议使用抽象类定义接口。

*/

/*
定义一个DB库 支持 mysql  mssql  mongodb

mysql  mssql  mongodb三个类里面都有同样的方法

*/


abstract class Db{   //当做接口   接口：就是约定 、规范
    late String uri;      //数据库的链接地址
    add(String data);
    save();
    delete();
}

class Mysql implements Db{  
  @override
  String uri;
  Mysql(this.uri);
  @override
  add(data) {
    // TODO: implement add
    print('这是mysql的add方法'+data);
  }
  @override
  delete() {
    // TODO: implement delete
    return null;
  }
  @override
  save() {
    // TODO: implement save
    return null;
  }
  remove(){     
  }  
}

class MsSql implements Db{
  @override
  late String uri;
  @override
  add(String data) {
    print('这是mssql的add方法'+data);
  }
  @override
  delete() {
    // TODO: implement delete
    return null;
  }
  @override
  save() {
    // TODO: implement save
    return null;
  }
}
main() {
  Mysql mysql=new Mysql('xxxxxx');
  mysql.add('1243214');
  
}
```

#### 14.多接口

```dart
/*
Dart中一个类实现多个接口：
*/

abstract class A{
  late String name;
  printA();
}

abstract class B{
  printB();
}

class C implements A,B{  
  @override
  late String name;  
  @override
  printA() {
    print('printA');
  }
  @override
  printB() {
    // TODO: implement printB
    return null;
  }

  
}


void main(){

  C c=new C();
  c.printA();


}
```

#### 15.mixins

```dart
/*
mixins的中文意思是混入，就是在类中混入其他功能。

在Dart中可以使用mixins实现类似多继承的功能


因为mixins使用的条件，随着Dart版本一直在变，这里讲的是Dart2.x中使用mixins的条件：

  1、作为mixins的类只能继承自Object，不能继承其他类
  2、作为mixins的类不能有构造函数
  3、一个类可以mixins多个mixins类
  4、mixins绝不是继承，也不是接口，而是一种全新的特性
*/

class Person{
  String name;
  num age;
  Person(this.name,this.age);
  printInfo(){
    print('${this.name}----${this.age}');
  }
  void run(){
    print("Person Run");
  }
}

class A {
  String info="this is A";
  void printA(){
    print("A");
  }
  void run(){
    print("A Run");
  }
}

class B {  
  void printB(){
    print("B");
  }
  void run(){
    print("B Run");
  }
}
//通过with实习混入
class C extends Person with B,A{
  C(String name, num age) : super(name, age);
  
}

void main(){  
  var c=new C('张三',20);  
  c.printInfo();
  // c.printB();
  // print(c.info);

   c.run();


}
/*
mixins的实例类型是什么？

很简单，mixins的类型就是其超类的子类型。

*/
```



### 11.泛型

```dart
/*

通俗理解：泛型就是解决 类 接口 方法的复用性、以及对不特定数据类型的支持(类型校验)

*/


//只能返回string类型的数据

  // String getData(String value){
  //     return value;
  // }
  

//同时支持返回 string类型 和int类型  （代码冗余）


  // String getData1(String value){
  //     return value;
  // }

  // int getData2(int value){
  //     return value;
  // }



//同时返回 string类型 和number类型       不指定类型可以解决这个问题


  // getData(value){
  //     return value;
  // }





//不指定类型放弃了类型检查。我们现在想实现的是传入什么 返回什么。比如:传入number 类型必须返回number类型  传入 string类型必须返回string类型
 
  // T getData<T>(T value){
  //     return value;
  // }

//泛型方法
  getData<T>(T value){
      return value;
  }

void main(){

    // print(getData(21));

    // print(getData('xxx'));

    // getData<String>('你好');

    print(getData<int>(12));

}
//泛型类
class MyList<T> {
  List list = <T>[];
  void add(T value) {
    this.list.add(value);
  }

  List getList() {
    return list;
  }
}
//泛型接口
abstract class Cache<T>{
  getByKey(String key);
  void setByKey(String key, T value);
}

class FlieCache<T> implements Cache<T>{
  @override
  getByKey(String key) {    
    return null;
  }

  @override
  void setByKey(String key, T value) {
   print("我是文件缓存 把key=${key}  value=${value}的数据写入到了文件中");
  }
}
```

#### 12.库相关

看官方文档

#### 13.Dart 2.13之后的些新特性Null safety、late关键字、空类型声明符?、非空断言!、required关键字

详细看文档

#### 1.Null safety

```dart
/*
  Null safety翻译成中文的意思是空安全。

  null safety 可以帮助开发者避免一些日常开发中很难被发现的错误，并且额外的好处是可以改善性能。

  Flutter2.2.0（2021年5月19日发布） 之后的版本都要求使用null safety。

  ? 可空类型

  ! 类型断言

*/

String? getData(apiUrl){
  if(apiUrl!=null){
    return "this is server data";
  }
  return null;
}
```

#### 2.late 关键字

```dart
/*
Null safety翻译成中文的意思是空安全。

late 关键字主要用于延迟初始化。

*/
class Person {
  late String name;
  late int age;

  void setName(String name, int age) {
    this.name = name;
    this.age = age;
  }

  String getName() {
    return "${this.name}---${this.age}";
  }
}

```



```dart
/*
和Java一样，dart也有接口，但是和Java还是有区别的。

  首先，dart的接口没有interface关键字定义接口，而是普通类或抽象类都可以作为接口被实现。

  同样使用implements关键字进行实现。

  但是dart的接口有点奇怪，如果实现的类是普通类，会将普通类和抽象中的属性的方法全部需要覆写一遍。
  
  而因为抽象类可以定义抽象方法，普通类不可以，所以一般如果要实现像Java接口那样的方式，一般会使用抽象类。

  建议使用抽象类定义接口。

*/

/*
定义一个DB库 支持 mysql  mssql  mongodb

mysql  mssql  mongodb三个类里面都有同样的方法

*/


abstract class Db{   //当做接口   接口：就是约定 、规范
    late String uri; //数据库的链接地址    
    add(String data);
    save();
    delete();
}
```

#### 3.required

```dart
/*
Null safety翻译成中文的意思是空安全。

required翻译成中文的意思是需要、依赖

required关键词:

    最开始 @required 是注解
    
    现在它已经作为内置修饰符。
    
    主要用于允许根据需要标记任何命名参数（函数或类），使得它们不为空。因为可选参数中必须有个 required 参数或者该参数有个默认值。

*/

// name 可以传入也可以不传入   age必须传入
class Person {
  String? name;   //可空属性
  int age;
  Person({this.name,required this.age});  //表示 name 和age 必须传入

  String getName() {
    return "${this.name}---${this.age}";
  }
}


void main(args) {
   Person p=new Person(
     name: "张三",
     age: 20
   );
   print(p.getName());  //张三---20


  Person p1=new Person(    
     age: 20
   );
   print(p1.getName());  //null---20
}
```







## 二.flutter学习

### 1.运行Flutter项目

**注意**：以下都是在终端中操作

```
flutter run
```

**r键**:		点击后热加载，也就算是重新加载吧。

**p键**:		显示网格，这个可以很好的掌握布局情况，工作中很有用。

**o键**:		切换android和ios的预览模式。

**q键**:		退出调试预览模式。



### 2.widget

Widget是Flutter应用程序用户界面的基本构建块。每个Widget都是用户界面一部分的不可变声明。 与其他将视图、控制器、布局和其他属性分离的框架不同，Flutter具有一致的统一对象模型：widget。

Flutter Widget采用现代响应式框架构建，这是从 React 中获得的灵感，中心思想是用widget构建你的UI。 Widget描述了他们的视图在给定其当前配置和状态时应该看起来像什么。当widget的状态发生变化时，widget会重新构建UI，Flutter会对比前后变化的不同， 以确定底层渲染树从一个状态转换到下一个状态所需的最小更改。

在编写应用程序时，通常会创建新的widget，这些widget是无状态的StatelessWidget或者是有状态的StatefulWidget， 具体的选择取决于您的widget是否需要管理一些状态。widget的主要工作是实现一个build函数，用以构建自身。一个widget通常由一些较低级别widget组成。Flutter框架将依次构建这些widget，直到构建到最底层的子widget时，这些最低层的widget通常为RenderObject，它会计算并描述widget的几何形状。

#### 1.runApp

`runApp()` 函数会持有传入的 [`Widget`](https://api.flutter-io.cn/flutter/widgets/Widget-class.html)，并且使它成为 widget 树中的根节点。在这个例子中，Widget 树有两个 widgets， [`Center`](https://api.flutter-io.cn/flutter/widgets/Center-class.html) widget 及其子 widget ——[`Text`](https://api.flutter-io.cn/flutter/widgets/Text-class.html) 。框架会强制让根 widget 铺满整个屏幕，也就是说“Hello World”会在屏幕上居中显示。在这个例子我们需要指定文字的方向，当使用 `MaterialApp` widget 时，你就无需考虑这一点，之后我们会进一步的描述。

在写应用的过程中，取决于是否需要管理状态，你通常会创建一个新的组件继承 [`StatelessWidget`](https://api.flutter-io.cn/flutter/widgets/StatelessWidget-class.html) 或 [`StatefulWidget`](https://api.flutter-io.cn/flutter/widgets/StatefulWidget-class.html)。 Widget 的主要工作是实现 [`build`](https://api.flutter-io.cn/flutter/widgets/StatelessWidget/build.html)方法，该方法根据其它较低级别的 widget 来描述这个 widget。框架会逐一构建这些 widget，直到最底层的描述 widget 几何形状的 [`RenderObject`](https://api.flutter-io.cn/flutter/rendering/RenderObject-class.html)。

```dart
void main() {
  //实例化可以不用写new
  //runApp是flutter提供的
  runApp(MyApp());
}
```



#### 2.**基础 Widget**

Flutter 自带了一套强大的基础 widgets，下面列出了一些常用的：

**[`Text`](https://api.flutter-io.cn/flutter/widgets/Text-class.html)**
`Text` widget 可以用来在应用内创建带样式的文本。

**[`Row`](https://api.flutter-io.cn/flutter/widgets/Row-class.html), [`Column`](https://api.flutter-io.cn/flutter/widgets/Column-class.html)**
这两个 flex widgets 可以让你在水平 (`Row`) 和垂直(`Column`) 方向创建灵活的布局。它是基于 web 的 flexbox 布局模型设计的。

**[`Stack`](https://api.flutter-io.cn/flutter/widgets/Stack-class.html)**
`Stack` widget 不是线性（水平或垂直）定位的，而是按照绘制顺序将 widget 堆叠在一起。你可以用 [`Positioned`](https://api.flutter-io.cn/flutter/widgets/Positioned-class.html) widget 作为`Stack` 的子 widget，以相对于 `Stack` 的上，右，下，左来定位它们。 Stack 是基于 Web 中的绝对位置布局模型设计的。

**[`Container`](https://api.flutter-io.cn/flutter/widgets/Container-class.html)**
`Container` widget 可以用来创建一个可见的矩形元素。 Container 可以使用 [`BoxDecoration`](https://api.flutter-io.cn/flutter/painting/BoxDecoration-class.html) 来进行装饰，如背景，边框，或阴影等。 `Container` 还可以设置外边距、内边距和尺寸的约束条件等。另外，`Container`可以使用矩阵在三维空间进行转换。



#### 3.第一个demo

```dart
//按fim引入该包
import 'dart:html';

import 'package:flutter/material.dart';

void main() {
  //实例化可以不用写new
  //runApp是flutter提供的
  runApp(MyApp());
}

//自定义组件
class MyApp extends StatelessWidget {
  //StatelessWidget无状态组件
  //StatefulWidget有状态组件

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('flutter demo'),
        ),
        body: HomeContent(),
      ),
      theme: ThemeData(
        primarySwatch: Colors.yellow
      ),
    );
  }
}


//定义主体内容组件
class HomeContent extends StatelessWidget{
  @override
  Widget build(BuildContext context){
    return Center(
      child: Text(
        "hello flutter 111",
        textDirection: TextDirection.ltr,
        style: TextStyle(
          fontSize: 40.0,
          color: Colors.lightBlue.shade900
        ),
      ),
    );
  }
}
```



#### 4.Container&Text

**1.Text**

| 名称            | 功能                                                         |
| --------------- | ------------------------------------------------------------ |
| textAlign       | 文本对齐方式（center 居中，left 左对齐，right 右对齐，justfy 两端对齐） |
| textDirection   | 文本方向（ltr 从左至右，rtl 从右至 左）                      |
| overflow        | 文字超出屏幕之后的处理方式（clip 裁剪，fade 渐隐，ellipsis 省略号） |
| textScaleFactor | 字体显示倍率                                                 |
| maxLines        | 文字显示最大行数                                             |
| style           | 字体的样式设置                                               |

**下面是 TextStyle 的参数 ：**

| 名称            | 功能                                                         |
| --------------- | ------------------------------------------------------------ |
| decoration      | 文字装饰线（none 没有线，lineThrough 删除线，overline 上划线，underline 下划线） |
| decorationColor | 文字装饰线颜色                                               |
| decorationStyle | 文字装饰线风格（[dashed,dotted]虚线， double 两根线，solid 一根实线，wavy 波浪线） |
| wordSpacing     | 单词间隙（如果是负值，会让单词变得更紧 凑                    |
| letterSpacing   | 字母间隙（如果是负值，会让字母变得更紧 凑）                  |
| fontStyle       | 文字样式（italic 斜体，normal 正常体）                       |
| fontSize        | 文字大小                                                     |
| color           | 文字颜色                                                     |
| fontWeight      | 字体粗细（bold 粗体，normal 正常体）                         |

[更多参数：https://docs.flutter.io/flutter/painting/TextStyle-class.html](https://docs.flutter.io/flutter/painting/TextStyle-class.html)



**2.Container**

container相当于前端的div容器

|    名称    | 功能                                                         |
| :--------: | ------------------------------------------------------------ |
| alignment  | topCenter：顶部居中对齐 topLeft：顶部左对齐 topRight：顶部右对齐 center：水平垂直居中对齐 centerLeft：垂直居中水平居左对齐 centerRight：垂直居中水平居右对齐 bottomCenter 底部居中对齐 bottomLeft：底部居左对齐 bottomRight：底部居右对齐 |
| decoration | ![image-20210905084932113](https://i.loli.net/2021/09/05/17pfXzcKydlFAb8.png) |
|   margin   | margin 属性是表示 Container 与外部其他组件的距离。 EdgeInsets.all(20.0), |
|  padding   | padding 就是 Container 的内边距， 指 Container 边缘与 Child 之间的距离 padding: EdgeInsets.all(10.0) |
| transform  | 让 Container 容易进行一些旋转之类的transform: Matrix4.rotationZ(0.2) |
|   height   | 容器高度                                                     |
|   width    | 容器宽度                                                     |
|   child    | 容器子元素                                                   |

[更多参数：https://api.flutter.dev/flutter/widgets/Container-class.html](https://api.flutter.dev/flutter/widgets/Container-class.html)

```dart
import 'dart:html';

import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('yeshifu'),
        ),
        body: MyBody(),
      ),
      theme: ThemeData(primarySwatch: Colors.blueGrey),
    );
  }
}

//主体内容组件
class MyBody extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return Center(
      child: Container(
          //text
        child: Text(
          "hello china",
          style: TextStyle(
            fontSize: 18.0, 
            color: Colors.blueAccent,
            fontStyle: FontStyle.italic,
            decoration: TextDecoration.underline,
            decorationColor: Colors.orange,
            letterSpacing: 5.0
          ),
          textAlign: TextAlign.center,
          textScaleFactor: 2.0,
          overflow: TextOverflow.fade,
        ),
          //container
        height: 300.0,
        width:300.0,
        decoration: BoxDecoration(
          color: Colors.deepPurpleAccent,
          border: Border.all(
            color: Colors.green,
            width: 2.0
          ),
          borderRadius: BorderRadius.all(
            Radius.circular(20.0)
          )
        ),
        padding:EdgeInsets.only(top: 20.0),
        //transform: Matrix4.translationValues(50, 0, 0),
        //transform: Matrix4.rotationZ(0.5),
        alignment: Alignment.bottomCenter,
      )
    );
  }
}

```



#### 5.图片

图片组件是显示图像的组件，Image 组件有很多构造函数，这里我们只给大家讲两个 

**Image.asset**，     本地图片    需要自行配置

**Image.network**        远程图片

**Image** **组件的常用属性**:

| 名称                                | 类型      | 说明                                                         |
| ----------------------------------- | --------- | ------------------------------------------------------------ |
| alignment                           | Alignment | 图片的对齐方式                                               |
| color             和 colorBlendMode |           | 设置图片的背景颜色，通常和 colorBlendMode 配合一起 使用，这样可以是图片颜色和背景色混合。上面的图片就是进行了颜色的混合，绿色背景和图片红色的混合 |
| fit                                 | BoxFit    | fit 属性用来控制图片的拉伸和挤压，这都是根据父容器来的。 BoxFit.fill:全图显示，图片会被拉伸，并充满父容器。 BoxFit.contain:全图显示，显示原比例，可能会有空隙。 BoxFit.cover：显示可能拉伸，可能裁切，充满（图片要 充满整个容器，还不变形）。 |
|                                     |           | BoxFit.fitWidth：宽度充满（横向充满），显示可能拉伸，可能裁切。 BoxFit.fitHeight ：高度充满（竖向充满）,显示可能拉伸，可能裁切。 BoxFit.scaleDown：效果和 contain 差不多，但是此属性不允许显示超过源图片大小，可小不可大。 |
| repeat                              | 平铺      | ImageRepeat.repeat : 横向和纵向都进行重复，直到铺满整个画布。 ImageRepeat.repeatX: 横向重复，纵向不重复。 ImageRepeat.repeatY：纵向重复，横向不重复。 |
| width                               |           | 宽度  一般结合 ClipOval 才能看到效果                         |
| height                              |           | 高度  一般结合 ClipOval 才能看到效果                         |

[更多属性参考：https://api.flutter.dev/flutter/widgets/Image-class.html](https://api.flutter.dev/flutter/widgets/Image-class.html)

```dart
//主体内容组件
class MyBody extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return Center(
      child: Container(
          //远程图片
        child: Image.network(
          "https://i.loli.net/2021/09/05/z7Oi5xLhNDlasU6.png",
          // alignment: Alignment.topRight,
          // fit:BoxFit.contain,
          // repeat:ImageRepeat.repeatX ,
        ), 
       /*  child: ClipOval(
          child: Image.network(
            "https://i.loli.net/2021/09/05/z7Oi5xLhNDlasU6.png",
            height: 400,
            width: 400,
            fit: BoxFit.cover,
          ),
        ), */
          //圆形图片设置和本地图片
        child: ClipOval(
          child: Image.asset(
            "images/2.png",
            height: 400,
            width: 400,
            fit: BoxFit.cover,
          ),
        ),
      ),
    );
  }
}
//圆形图片设置2
/*         height: 300,
        width: 300,
        decoration: BoxDecoration(
          color: Colors.brown,
          /* borderRadius: BorderRadius.all(
            Radius.circular(150)
          ), */
          borderRadius: BorderRadius.circular(150),
          image: DecorationImage(
            image: NetworkImage(
              "https://i.loli.net/2021/09/05/z7Oi5xLhNDlasU6.png"
            ),
            fit: BoxFit.cover
            )
        ), */
```



**注意**：flutter2.x以后引入远程图片的时候必须使用**https协议**

**推荐 使用ClipOval组件设置圆形图片**



##### **本地图片配置**

1.新建assets文件夹

在工程名上右键，选择New->Directory，输入assets

2.修改pubspec.yaml

取消掉assets相关的注释，把图片copy到assets目录下，添加如下的内容

然后，在代码种使用AssetImage就可以加载图片了，如下：

```dart
class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: Text('容器组件示例'),
        ),
        body: Center(
          child: Image(
            image: Image.assert('assets/girl.jpg'),
          )
        ),
      )
    );
  }
}
```

**[详细见官网](https://flutter.cn/docs/development/ui/assets-and-images#loading-images)**



#### 6.列表

列表布局是我们项目开发中最常用的一种布局方式。Flutter 中我们可以通过 ListView 来定义 

列表项，支持垂直和水平方向展示。通过一个属性就可以控制列表的显示方向。列表有一下 

分类： 

1、垂直列表 

2、垂直图文列表 

3、水平列表 

4、动态列表 

5、矩阵式列表

**Flutter** **列表参数** ：

| 名称            | 类型               | 说明                                            |
| --------------- | ------------------ | ----------------------------------------------- |
| scrollDirection | Axis               | Axis.horizontal 水平列表 Axis.vertical 垂直列表 |
| padding         | EdgeInsetsGeometry | 内边距                                          |
| resolve         | bool               | 组件反向排序                                    |
| children        | List<Widget>       | 列表元素                                        |

```dart
import 'package:flutter/material.dart';

import 'res/listData.dart';

void main() => runApp(MyApp());
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return MaterialApp(
      home: Scaffold(
      appBar: AppBar(title: Text('FlutterDemo')),
      body: HomeContent(),
    ));
  }
}
class HomeContent extends StatelessWidget {  


  //自定义方法
  Widget _getListData(context,index){
      //LIstTile
        return ListTile(           
            title: Text(listData[index]["title"]),
            leading:Image.network(listData[index]["imageUrl"]),          
            subtitle:Text(listData[index]["author"])
        );
  }

  @override
  Widget build(BuildContext context) {    
    // TODO: implement build
      //builder方法生成动态列表
    return ListView.builder(
        itemCount:listData.length,
        itemBuilder:this._getListData
    );
  }
}
```

**ListTile列表项**





#### 7.**GridView**

**GridView** **创建网格列表有多种方式，下面我们主要介绍两种。**

1、可以通过 GridView.count 实现网格布局 

2、通过 GridView.builder 实现网格布局

![image-20210905191308556](https://i.loli.net/2021/09/05/CSPmepbDzlufRN8.png)

```dart
import 'dart:html';
import 'dart:ui';

import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('yeshifu'),
        ),
        body: MyBody(),
      ),
      theme: ThemeData(primarySwatch: Colors.blueGrey),
    );
  }
}

//主体内容组件
class MyBody extends StatelessWidget {
  List<Widget> list = [];
  List<Widget> _getData() {
    for (int i = 0; i < 20; i++) {
      this.list.add(Container(
            child: Text(
              "data$i",
              textAlign: TextAlign.center,
              ),
            //height: 200,
            alignment: Alignment.center,
            width: 100,
            decoration: BoxDecoration(
                color: Colors.purple,
                border: Border.all(
                  color: Colors.brown,
                  width: 2,
                )),
          ));
    }

    return this.list;
  }

  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    /* return ListView(
      children: this._getData()
    ); */
    return GridView.count(
      crossAxisCount: 2,
      crossAxisSpacing: 10,
      padding: EdgeInsets.all(10),
      mainAxisSpacing: 10,
      children: this._getData(),
      childAspectRatio: 0.7,//宽高比
    );
  }
}

```



**动态网格列表**

```dart
import 'package:flutter/material.dart';

import 'res/listData.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('FlutterDemo')),
        body: LayoutDemo(),
      ));
  }
}
class LayoutDemo extends StatelessWidget {  


  Widget _getListData (context,index) {
        return Container(            
            child:Column(
                children: <Widget>[
                  Image.network(listData[index]['imageUrl']),
                  SizedBox(height: 12),
                  Text(
                    listData[index]['title'],
                    textAlign: TextAlign.center,
                    style: TextStyle(
                      fontSize: 20
                    ),
                  )
                ],

            ),
            decoration: BoxDecoration(
              border: Border.all(
                color:Color.fromRGBO(233, 233,233, 0.9),
                width: 1
              )
            ),
              
            // height: 400,  //设置高度没有反应
          );
  }


  @override
  Widget build(BuildContext context) {    
    return GridView.builder(
        
        //注意
        gridDelegate:SliverGridDelegateWithFixedCrossAxisCount(
          crossAxisSpacing:10.0 ,   //水平子 Widget 之间间距
          mainAxisSpacing: 10.0,    //垂直子 Widget 之间间距          
          crossAxisCount: 2,  //一行的 Widget 数量
        ),
        itemCount: listData.length,
        itemBuilder:this._getListData,
    );
  }
}

```



#### 8.**Paddiing** **组件**

在 html 中常见的布局标签都有 padding 属性，但是 Flutter 中很多 Widget 是没有 padding 属 

性。这个时候我们可以用 Padding 组件处理容器与子元素直接的间距。

![image-20210906183510404](https://i.loli.net/2021/09/06/fdDZylSkvz9be1m.png)



#### 9.**Row** **水平布局组件** 

![image-20210906183555907](https://i.loli.net/2021/09/06/4NbOqIQcxUwLe1B.png)



#### 10.**Column** **垂直布局组件**

![image-20210906183638840](https://i.loli.net/2021/09/06/VXPzRTMZSdbe8oa.png)



#### 11.**Expanded** **类似** **Web** **中的** **Flex** **布局**

Expanded 可以用在 Row 和 Column 布局中

![image-20210906183742847](https://i.loli.net/2021/09/06/yt9Gufp6QJzSbFP.png)



```dart
import 'dart:html';
import 'dart:ui';

import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('yeshifu'),
        ),
        body: MyBody(),
      ),
      theme: ThemeData(primarySwatch: Colors.blueGrey),
    );
  }
}

//主体内容组件
class MyBody extends StatelessWidget {

  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    /* return ListView(
      children: this._getData()
    ); */
    return Column(
      children: [
        Container(
          height: 200,
          color: Colors.cyanAccent,
        ),
        SizedBox(
          height: 10,
        ),
        Row(
          children: [
            Expanded(
                flex: 2,
                child: Image.network(
                  "https://i.loli.net/2021/09/05/z7Oi5xLhNDlasU6.png",
                  height: 200,
                  fit: BoxFit.fitWidth,
                )),
            SizedBox(width: 10,),
            Expanded(
                flex: 1,
                child: Column(
                  children: [
                    Container(
                      color: Colors.red,
                      //width: 100,
                      height:95,
                    ),
                    SizedBox(height: 10,),
                    Container(
                      color: Colors.blue,
                      //width: 100,
                      height: 95,
                    )
                  ],
                ))
          ],
        )
      ],
    );
  }
}

```



#### 12.**Stack** **组件** 

Stack 表示堆的意思，我们可以用 Stack 或者 Stack 结合 Align 或者 Stack 结合 Positiond 来实 

现页面的定位布局

![image-20210906184024167](https://i.loli.net/2021/09/06/nduH36s5tE4CyiO.png)

**Stack Align**

Stack 组件中结合 Align 组件可以控制每个子元素的显示位置

![image-20210906184105902](https://i.loli.net/2021/09/06/UIbjwpsi7DYfLtB.png)

**Stack Positioned**

Stack 组件中结合 Positioned 组件也可以控制每个子元素的显示位置 

![image-20210906184230647](https://i.loli.net/2021/09/06/pJQF26YmEBxIWV3.png)

```dart
import 'dart:html';
import 'dart:ui';

import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('yeshifu'),
        ),
        body: MyBody(),
      ),
      theme: ThemeData(primarySwatch: Colors.blueGrey),
    );
  }
}

//主体内容组件
class MyBody extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    /* return ListView(
      children: this._getData()
    ); */
    return Center(
        child: Container(
      height: 300,
      width: 200,
      decoration: BoxDecoration(
          image: DecorationImage(
              image: NetworkImage(
        "https://i.loli.net/2021/09/05/z7Oi5xLhNDlasU6.png",
      ))),
      child: Stack(
        children: [
          Positioned(
              top: 50,
              left: 50,
              child: Text(
                "测试内容",
                style: TextStyle(
                  color: Colors.red,
                  fontSize: 20
                ),
              )),
          Align(
            alignment: Alignment(0, 0.8),
            child: Text(
              "测试内容2",
              style: TextStyle(
                color: Colors.blue,
                fontSize: 20
              ),
            ),
          )
        ],
      ),
    ));
  }
}

```



#### 13.**AspectRatio** **组件** 

**AspectRatio** 的作用是根据设置调整子元素 child 的宽高比。 

**AspectRatio** 首先会在布局限制条件允许的范围内尽可能的扩展，widget 的**高度是由宽** 

**度和比率**决定的，类似于 BoxFit 中的 contain，按照固定比率去尽量占满区域。 

如果在满足所有限制条件过后无法找到一个可行的尺寸，AspectRatio 最终将会去优先 

适应布局限制条件，而忽略所设置的比率。 

![image-20210906184450953](https://i.loli.net/2021/09/06/wuU1KJVLFARIiD5.png)



#### 14.**Card** **组件**

Card 是卡片组件块，内容可以由大多数类型的 Widget 构成，Card 具有圆角和阴影，这让它 

看起来有立体感。 

![image-20210906184607481](https://i.loli.net/2021/09/06/IcaAN8sODtk3B1m.png)

```dart
import 'package:flutter/material.dart';
import 'res/listData.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return MaterialApp(
        home: Scaffold(
        appBar: AppBar(title: Text('FlutterDemo')),
        body: LayoutDemo(),
      ));
  }
}
class LayoutDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return ListView(
      children: listData.map((value){
        return Card(
          margin: EdgeInsets.all(10),
          child:Column(
              children: <Widget>[
                  AspectRatio(
                    aspectRatio: 20/9,
                    child: Image.network(value["imageUrl"],fit: BoxFit.cover,),
                  ),
                  ListTile(
                    leading: CircleAvatar(
                      backgroundImage:NetworkImage(value["imageUrl"])
                    ),
                    title: Text(value["title"]),
                    subtitle: Text(value["description"],maxLines: 1,overflow: TextOverflow.ellipsis),                    
                  )
              ],
          ),

        );

      }).toList(),
    );
  }
}
```



#### 15.**Wrap** **组件**

Wrap 可以实现流布局，单行的 Wrap 跟 Row 表现几乎一致，单列的 Wrap 则跟 Row 表 

现几乎一致。但 Row 与 Column 都是单行单列的，Wrap 则突破了这个限制，mainAxis 上空 

间不足时，则向 crossAxis 上去扩展显示。

![image-20210906184935966](https://i.loli.net/2021/09/06/OkABpD5jvqoUhxi.png)



#### 16.**Flutter** **中自定义有状态组件**

在 Flutter 中自定义组件其实就是一个类，这个类需要继承 StatelessWidget/StatefulWidget。 

**StatelessWidget** 是无状态组件，状态不可变的 widget 

**StatefulWidget** 是有状态组件，持有的状态可能在 widget 生命周期改变。通俗的讲：如果我 

们想改变页面中的数据的话这个时候就需要用到 **StatefulWidget**

```dart
import 'dart:html';
import 'dart:ui';

import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('yeshifu'),
        ),
        body: MyBody(),
      ),
      theme: ThemeData(primarySwatch: Colors.blueGrey),
    );
  }
}

//主体内容组件
class MyBody extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    /* return ListView(
      children: this._getData()
    ); */
    return HomePage();
  }
}
//自定义有状态组件
//通过statefulW生成
class HomePage extends StatefulWidget {
  HomePage({Key? key}) : super(key: key);

  @override
  _HomePageState createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  int num = 1;
  @override
  Widget build(BuildContext context) {
    return Container(
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          Chip(label: Text("${this.num}")),
          SizedBox(
            height: 20,
          ),
          ElevatedButton(
              onPressed: () {
                setState(() {
                  this.num++;
                });
              },
              child: Text('按钮'))
        ],
      ),
    );
  }
}

```



#### 17.**BottomNavigationBar** **组件**

BottomNavigationBar 是底部导航条，可以让我们定义底部 Tab 切换，bottomNavigationBar 

是 Scaffold 组件的参数。

**BottomNavigationBar** **常见的属性**

![image-20210906185556886](https://i.loli.net/2021/09/06/BWySrXvTiF3eRE2.png)



#### 18.路由

Flutter 中的路由通俗的讲就是页面跳转。在 Flutter 中通过 Navigator 组件管理路由导航。 

并提供了管理堆栈的方法。如：Navigator.push 和 Navigator.pop 

Flutter 中给我们提供了两种配置路由跳转的方式：

1、基本路由 2、命名路由



##### 1.基本路由

比如我们现在想从 HomePage 组件跳转到 SearchPage 组件。

​	**1**、需要在**HomPage** **中引入** **SearchPage.dart**

​	**2、在 HomePage** **中通过下面方法跳转**

```dart
ElevatedButton(
              onPressed: () {
                //路由跳转
                Navigator.of(context).push(
                    MaterialPageRoute(
                    builder: (context) => SearchPage()
                    ),
                );
              },
              child: Text("跳转到其他页面")
           )
```



传值查看官方文档



##### 2.命名路由

**1**、配置路由

```dart
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // TODO: implement build
    return MaterialApp(
      home: Tabs(),
      theme: ThemeData(primarySwatch: Colors.blueGrey),
        //路由配置
      routes: {
        "/search": (context) => SearchPage(
              params: {"age": 18},
            ),
        "/appbartest": (context) => AppBarTestPage(),
        "/tabbarpage": (context) => TabbarContollerPage()
      },
        //关闭debug图标
      debugShowCheckedModeBanner: false,
        //默认显示路由
      initialRoute: "/appbartest",
    );
  }
}
```



**2**、路由跳转 

```dart
ElevatedButton(
              onPressed: () {
                Navigator.pushNamed(context, "/search", arguments: "你好呀呀呀呀");
              },
              child: Text("跳转到搜索页面")),
```



**3.传值**

```dart
final args = ModalRoute.of(context)!.settings.arguments;
//在build里面，返回
```

[官方文档](https://flutter.cn/docs/cookbook/navigation/navigate-with-arguments)

**注意：也可以再创建类的时候设置传值**





##### 3.**替换路由**

比如我们从用户中心页面跳转到了 registerFirst 页面，然后从 registerFirst 页面通过 

pushReplacementNamed 跳转到了 registerSecond 页面。这个时候当我们点击 registerSecond 

的返回按钮的时候它会直接返回到用户中心。 

```dart
Navigator.of(context).pushReplacementNamed('/registerSecond');
```



##### 4.**返回到根路由**

比如我们从用户中心跳转到 registerFirst 页面，然后从 registerFirst 页面跳转到 registerSecond 

页面，然后从 registerSecond 跳转到了 registerThird 页面。这个时候我们想的是 registerThird 

注册成功后返回到用户中心。 这个时候就用到了返回到根路由的方法。

```dart
//scaffold中参数
floatingActionButton: FloatingActionButton(
  onPressed: () {
      //返回根路由
   Navigator.of(context).pushAndRemoveUntil(
        MaterialPageRoute(
            builder: (context) => Tabs(
                  index: 1,
                )),
        (route) => false);
  },
  child: Text("返回"),
),
```



#### 19.**AppBar** **自定义顶部按钮**

![image-20210908175636869](https://i.loli.net/2021/09/08/OyCN8ueAvmZf5Bt.png)



```dart
class AppBarTestPage extends StatelessWidget {
  const AppBarTestPage({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return DefaultTabController(
        length: 2,
        child: Scaffold(
            appBar: AppBar(
              title: Text("appbar演示"),
              actions: [
                IconButton(
                  icon: Icon(Icons.menu),
                  onPressed: () {},
                ),
                IconButton(onPressed: () {}, icon: Icon(Icons.search))
              ],
              bottom: TabBar(
                tabs: [
                  Tab(
                    text: "热门",
                  ),
                  Tab(
                    text: "推荐",
                  ),
                ],
              ),
              //backgroundColor: Colors.red,
              centerTitle: true,
            ),
            body: TabBarView(
              children: [
                Container(
                  child: Text("热门"),
                ),
                Container(
                  child: Text("推荐 "),
                )
              ],
            )));
  }
}
```



#### 20.**AppBar** **中自定义** **TabBar**

**TabBar** **常见属性：**

![image-20210908175917624](https://i.loli.net/2021/09/08/a3liP4UgruxYDMo.png)



另一种方法（推荐使用）

```dart
class TabbarContollerPage extends StatefulWidget {
  TabbarContollerPage({Key? key}) : super(key: key);

  @override
  _TabbarContollerPageState createState() => _TabbarContollerPageState();
}

//先混入SingleTickerProviderStateMixin
class _TabbarContollerPageState extends State<TabbarContollerPage>
    with SingleTickerProviderStateMixin {
    //
  late TabController _tabController;
  @override
    //生命周期函数
  void initState() {
    super.initState();
      //实例化
    this._tabController = new TabController(length: 2, vsync: this);
    //事件监听
    this._tabController.addListener(() {
      print(_tabController.index);
    });
  }

  @override
  void dispose() {
    // TODO: implement dispose
    super.dispose();
    _tabController.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("TabbarController"),
        bottom: TabBar(
            //必填
          controller: this._tabController,
          tabs: [
            Tab(
              text: "自定义",
            ),
            Tab(
              text: "tabbar",
            ),
          ],
        ),
      ),
      body: TabBarView(
          //必填
        controller: this._tabController,
        children: [
          Text("1"),
          Text("2"),
        ],
      ),
    );
  }
}

```

如外面已经嵌套一层scaffold

里面return DefaultTabController

特殊小技巧：**把** **TabBar** **放在导航最顶部**



#### 21.**Drawer** **侧边栏** 

在 Scaffold 组件里面传入 drawer 参数可以定义左侧边栏，传入 endDrawer 可以定义右侧边 

栏。侧边栏默认是隐藏的，我们可以通过手指滑动显示侧边栏，也可以通过点击按钮显示侧 

边栏。 

```dart
return Scaffold(
      appBar: AppBar(
        title: Text("Flutter App"),
      ),
      drawer: Drawer(
        child: Text('左侧边栏'),
      ),
      endDrawer: Drawer(
        child: Text('右侧侧边栏'),
      ),
    );
```



**DrawerHeader**

**常见属性：**

![image-20210910091220136](https://i.loli.net/2021/09/10/4MsYgEVTx9PHnLX.png)



**UserAccountsDrawerHeader**

![image-20210910091321159](https://i.loli.net/2021/09/10/yk2naE5OWtepzBm.png)



```dart
drawer: Drawer(
        child: Column(
          children: [
            Row(
              children: [
                Expanded(
                  /*child:  DrawerHeader(
                  child: Text("我的空间"),
                  decoration: BoxDecoration(
                    image: DecorationImage(image:NetworkImage(
                      "https://i.loli.net/2021/09/05/BNUoCXWmVZaTFtD.png", 
                    ),
                    fit: BoxFit.cover,
                  ),
                  ),
                  ), */

                  child: UserAccountsDrawerHeader(
                    accountName: Text("叶师傅"),
                    accountEmail: Text("yexiyue666@qq.com"),
                    currentAccountPicture: CircleAvatar(
                      backgroundImage: NetworkImage(
                          "https://i.loli.net/2021/09/05/BNUoCXWmVZaTFtD.png"),
                    ),
                    decoration: BoxDecoration(
                      image: DecorationImage(
                          image: NetworkImage(
                              "https://i.loli.net/2021/09/05/dV8UMrGksEJyoIw.png"),
                          fit: BoxFit.cover,
                          alignment: Alignment.centerRight),
                    ),
                  ),
                )
              ],
            ),
            ListTile(
              leading: CircleAvatar(
                backgroundImage: NetworkImage(
                    "https://i.loli.net/2021/09/05/dV8UMrGksEJyoIw.png"),
              ),
              title: Text("我的头像"),
              //点击触发事件
              onTap: () {
                //关闭侧边栏，侧边栏也相当于一个页面
                Navigator.pop(context);
                Navigator.push(context,
                    MaterialPageRoute(builder: (context) => MyCircleAvatar()));
              },
            ),
            Divider()//底部横线
          ],
        ),
      ),
```



#### 22.按钮

**ElevatedButton** ：凸起的按钮，其实就是 Material Design 风格的 Button 

**TextButton** ：扁平化的按钮 

**OutlinedButton**：线框按钮 

**IconButton** ：图标按钮 

**ButtonBar**:按钮组 

**FloatingActionButton:**浮动按钮



```dart
Container(
                height: 50,
                width: 200,
                child: ElevatedButton(
                  onPressed: () {},
                  child: Text("按钮"),
                  style: ButtonStyle(
                    backgroundColor: MaterialStateProperty.all(Colors.red),
                    foregroundColor: MaterialStateProperty.all(Colors.purple),
                    elevation: MaterialStateProperty.all(30),
                    shadowColor: MaterialStateProperty.all(Colors.red),
                    shape: MaterialStateProperty.all(RoundedRectangleBorder(
                        borderRadius: BorderRadius.circular(50))),
                    overlayColor:MaterialStateProperty.all(Colors.grey),
                  ),
                ),
              ),
```



[更多用法看官网](https://api.flutter-io.cn/flutter/material/ButtonStyle-class.html)

**FloatingActionButton 简称 FAB** **,**可以实现浮动按钮，也可以实现类似闲鱼 app 的地步凸 起导航 

![image-20210910092256003](https://i.loli.net/2021/09/10/m7FZiBYy1gelhU6.png)



#### 23.**常用表单**

**TextField** **文本框组件**

**TextField** **表单常见属性：** 

![image-20210912193334343](https://i.loli.net/2021/09/12/cEjDGwySqkbAB4d.png)



**Checkbox**、**CheckboxListTile** **多选框组件**

![image-20210912193504806](https://i.loli.net/2021/09/12/K3biywWnlMCJcpB.png)

![image-20210912193534334](https://i.loli.net/2021/09/12/KtNJYXugOWMQ1V5.png)



**Radio**、**RadioListTile** **单选按钮组件**

![image-20210912193621211](https://i.loli.net/2021/09/12/ZCPeIvRqhpg6zc8.png)



**Switch**

![image-20210912193702584](https://i.loli.net/2021/09/12/5bUuDH498YjR3Gr.png)



更多用法看官网



#### 24.日期

**第三方库** **date_format**

date_format 可以格式化日期 文档：https://pub.dev/packages/date_format

```dart
class StudentFormPage extends StatefulWidget {
  StudentFormPage({Key? key}) : super(key: key);

  @override
  _StudentFormPageState createState() => _StudentFormPageState();
}

class _StudentFormPageState extends State<StudentFormPage> {
  //时间戳
  var now = DateTime.now();
  var time;
  var timenow;
  var shijian;
  var threetime;
  _showDatePicker(context) async {
    time = await showDatePicker(
        context: context,
        initialDate: now,
        firstDate: DateTime(1974),
        lastDate: DateTime(2022));
    return time;
  }

  _showTimePicker(context) async {
    var time;
    time = await showTimePicker(context: context, initialTime: TimeOfDay.now());
    setState(() {
      if (time != null) {
        shijian = time;
      }
    });
  }

  @override
  void initState() {
    // TODO: implement initState
    super.initState();
    //time = now.millisecondsSinceEpoch;
    //timenow = DateTime.fromMillisecondsSinceEpoch(time);
    timenow = formatDate(DateTime.now(), [yyyy, '-', mm, '-', dd]);
    shijian = TimeOfDay.now();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: Text("时间"),
          backgroundColor: Colors.orange,
        ),
        body: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            InkWell(
              child: Expanded(
                  child: Row(
                mainAxisAlignment: MainAxisAlignment.center,
                children: [
                  Text(
                    "${timenow}",
                    style: TextStyle(color: Colors.orange),
                  ),
                  Icon(Icons.arrow_drop_down)
                ],
              )),
              onTap: () {
                setState(() {
                  timenow = formatDate(
                      _showDatePicker(context), [yyyy, '-', mm, '-', dd]);
                });
              },
            ),
            InkWell(
              child: Row(
                mainAxisAlignment: MainAxisAlignment.center,
                children: [
                  Text(
                    "${shijian.format(context)}",
                    style: TextStyle(color: Colors.orange),
                  ),
                  Icon(Icons.arrow_drop_down)
                ],
              ),
              onTap: () {
                _showTimePicker(context);
              },
            ),
            InkWell(
              child: Row(
                mainAxisAlignment: MainAxisAlignment.center,
                children: [
                  Text(
                    "${threetime != null ? formatDate(threetime, [
                            yyyy,
                            '-',
                            mm,
                            '-',
                            dd
                          ]) : "2021-9-1"}",
                    style: TextStyle(color: Colors.orange),
                  ),
                  Icon(Icons.arrow_drop_down)
                ],
              ),
              onTap: () {
                DatePicker.showDatePicker(context,
                    minTime: DateTime(2018, 3, 5),
                    maxTime: DateTime(2030, 6, 7),
                    locale: LocaleType.zh,
                    currentTime: DateTime.now(), onConfirm: (v) {
                  setState(
                    () {
                      threetime = v;
                    },
                  );
                }, onChanged: (value) {
                  setState(
                    () {
                      threetime = value;
                    },
                  );
                });
              },
            )
          ],
        ));
  }
}
```



#### 25.dialog

```dart
//对话框
class Dialog extends StatefulWidget {
  Dialog({Key? key}) : super(key: key);

  @override
  _DialogState createState() => _DialogState();
}

class _DialogState extends State<Dialog> {

  var data;
  var str=null;
  _getdata() async{
    data=await Dio().get("https://api.uixsj.cn/hitokoto/get?type=social");
    setState(() {
      str=data;
    });
  }
  @override
  void initState() { 
    super.initState();
    this._getdata();
  }
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text("对话框"),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.spaceAround,
          children: [
              //alert dialog
            ElevatedButton(
                onPressed: () {
                  showDialog(
                      context: context,
                      builder: (context) {
                        return AlertDialog(
                          title: Text("提示信息"),
                          content: Text("确认删除吗？"),
                          actions: [
                            TextButton(
                                onPressed: () {
                                  Navigator.pop(context);
                                },
                                child: Text("取消")),
                            TextButton(
                                onPressed: () {
                                  Navigator.pop(context);
                                },
                                child: Text("确认"))
                          ],
                        );
                      });
                },
                child: Text("Alert Dialog")),
              //simple dialog
            ElevatedButton(
                onPressed: () {
                  showDialog(
                      context: context,
                      builder: (context) {
                        return SimpleDialog(
                          title: Text("请选择"),
                          children: [
                            SimpleDialogOption(
                              onPressed: () {
                                Navigator.pop(context);
                              },
                              child: Text("data1"),
                            ),
                            Divider(),
                            SimpleDialogOption(
                              onPressed: () {
                                Navigator.pop(context);
                              },
                              child: Text("data2"),
                            ),
                            Divider(),
                            SimpleDialogOption(
                              onPressed: () {
                                Navigator.pop(context);
                              },
                              child: Text("data3"),
                            ),
                          ],
                        );
                      });
                },
                child: Text("simple Dialog")),
              //showModalBottomSheet
            ElevatedButton(
                onPressed: () {
                  showModalBottomSheet(
                      context: context,
                      //backgroundColor:Colors.blueGrey,
                      builder: (context) {
                        return Container(
                          height: 200,
                          /* decoration: BoxDecoration(color: Colors.orange), */
                          child: Column(
                            mainAxisAlignment: MainAxisAlignment.end,
                            children: [
                              Text("$str"),
                              ElevatedButton(onPressed: (){
                                setState(() {
                                  this._getdata();
                                });
                              }, child:Text("刷新") ),
                              Row(
                                children: [
                                  TextButton(
                                      onPressed: () {
                                        Navigator.pop(context);
                                      },
                                      child: Text("确认")),
                                  TextButton(
                                      onPressed: () {
                                        Navigator.pop(context);
                                      },
                                      child: Text("取消"))
                                ],
                              )
                            ],
                          ),
                        );
                      });
                },
                child: Text("BottomSheet Dialog")),
              //第三方Fluttertoast
            ElevatedButton(
                onPressed: () {
                  Fluttertoast.showToast(
                      msg: "登录成功",
                      toastLength: Toast.LENGTH_SHORT,
                      gravity: ToastGravity.BOTTOM,
                      //webPosition:ToastGravity.BOTTOM,
                      timeInSecForIosWeb: 2,
                      backgroundColor: Colors.black26,
                      textColor: Colors.white,
                      fontSize: 16.0);
                },
                child: Text("showToast Dialog")),
              //自定义
            ElevatedButton(
                onPressed: () {
                  Map list={
                    "name":"张三",
                    "age":18
                  };
                  print(jsonEncode(list));
                  showDialog(context: context, builder: (context){
                    return MyDialog();
                  });
                },
                child: Text("自定义dialog")),
          ],
        ),
      ),
    );
  }
}


//自定义dialog
class MyDialog extends Dialog{
  Widget build(BuildContext context) {
    return Material(
      child: Container(
        height: 200,
        width: 200,
        decoration: BoxDecoration(color: Colors.red),
        child: Center(
          child: Text("data"),
        ),
      ),
      type:MaterialType.transparency ,
    );
  }
}
```



#### 26.发送请求

[dio](https://pub.dev/packages/dio)

[http](https://pub.dev/packages/http)



#### 27.轮播图

[**flutter_swiper**](https://pub.dev/packages/flutter_swiper)

