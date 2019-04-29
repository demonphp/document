### 常见对象(Scanner的概述和方法介绍)(掌握)
* A:Scanner的概述
* B:Scanner的构造方法原理
	* Scanner(InputStream source)
	* System类下有一个静态的字段：
		* public static final InputStream in; 标准的输入流，对应着键盘录入。

* C:一般方法
	* hasNextXxx()  判断是否还有下一个输入项,其中Xxx可以是Int,Double等。如果需要判断是否包含下一个字符串，则可以省略Xxx
	* nextXxx()  获取下一个输入项。Xxx的含义和上个方法中的Xxx相同,默认情况下，Scanner使用空格，回车等作为分隔符


### 常见对象(Scanner获取数据出现的小问题及解决方案)(掌握)
* A:两个常用的方法：
	* public int nextInt():获取一个int类型的值
	* public String nextLine():获取一个String类型的值
* B:案例演示
	* a:先演示获取多个int值，多个String值的情况
	* b:再演示先获取int值，然后获取String值出现问题
	* c:问题解决方案
		* 第一种：先获取一个数值后，在创建一个新的键盘录入对象获取字符串。
		* 第二种：把所有的数据都先按照字符串获取，然后要什么，你就对应的转换为什么。(后面讲)

### 常见对象(String类的概述)(掌握)
* A:String类的概述
	* 通过JDK提供的API，查看String类的说明

	* 可以看到这样的两句话。
		* a:字符串字面值"abc"也可以看成是一个字符串对象。
		* b:字符串是常量，一旦被赋值，就不能被改变。

### 常见对象(String类的构造方法)(掌握)
* A:常见构造方法
	* public String():空构造
	* public String(byte[] bytes):把字节数组转成字符串
	* public String(byte[] bytes,int index,int length):把字节数组的一部分转成字符串
	* public String(char[] value):把字符数组转成字符串
	* public String(char[] value,int index,int count):把字符数组的一部分转成字符串
	* public String(String original):把字符串常量值转成字符串
* B:案例演示
	* 演示String类的常见构造方法

```java
String s1 = new String();
System.out.println(s1);

byte[] arr1 = {97,98,99};		
String s2 = new String(arr1);			//解码,将计算机读的懂的转换成我们读的懂
System.out.println(s2);

byte[] arr2 = {97,98,99,100,101,102};
String s3 = new String(arr2,2,3);		//将arr2字节数组从2索引开始转换3个
System.out.println(s3);

char[] arr3 = {'a','b','c','d','e'};	//将字符数组转换成字符串
String s4 = new String(arr3);
System.out.println(s4);

String s5 = new String(arr3,1,3);		//将arr3字符数组,从1索引开始转换3个
System.out.println(s5);

String s6 = new String("heima");
System.out.println(s6);
```

### 常见对象(String类的常见面试题)(掌握)
* 1.判断定义为String类型的s1和s2是否相等
	* String s1 = "abc";
	* String s2 = "abc";
	* System.out.println(s1 == s2); 				//true
	* System.out.println(s1.equals(s2)); 		//true

* 2.下面这句话在内存中创建了几个对象?
	* String s1 = new String("abc");			

* 3.判断定义为String类型的s1和s2是否相等
	* String s1 = new String("abc");			
	* String s2 = "abc";
	* System.out.println(s1 == s2);					//false
	* System.out.println(s1.equals(s2));		//true

* 4.判断定义为String类型的s1和s2是否相等
	* String s1 = "a" + "b" + "c";
	* String s2 = "abc";
	* System.out.println(s1 == s2);				//true
	* System.out.println(s1.equals(s2));  //true

* 5.判断定义为String类型的s1和s2是否相等
	* String s1 = "ab";
	* String s2 = "abc";
	* String s3 = s1 + "c";
	* System.out.println(s3 == s2);				 //false
	* System.out.println(s3.equals(s2));   //true

### 常见对象(String类的判断功能)(掌握)
* A:String类的判断功能
	* boolean equals(Object obj):比较字符串的内容是否相同,区分大小写
	* boolean equalsIgnoreCase(String str):比较字符串的内容是否相同,忽略大小写
	* boolean contains(String str):判断大字符串中是否包含小字符串
	* boolean startsWith(String str):判断字符串是否以某个指定的字符串开头
	* boolean endsWith(String str):判断字符串是否以某个指定的字符串结尾
	* boolean isEmpty():判断字符串是否为空。


### 常见对象(String类的获取功能)(掌握)
* A:String类的获取功能
	* int length():获取字符串的长度。
	* char charAt(int index):获取指定索引位置的字符
	* int indexOf(int ch):返回指定字符在此字符串中第一次出现处的索引。
	* int indexOf(String str):返回指定字符串在此字符串中第一次出现处的索引。
	* int indexOf(int ch,int fromIndex):返回指定字符在此字符串中从指定位置后第一次出现处的索引。
	* int indexOf(String str,int fromIndex):返回指定字符串在此字符串中从指定位置后第一次出现处的索引。
	* lastIndexOf
	* String substring(int start):从指定位置开始截取字符串,默认到末尾。
	* String substring(int start,int end):从指定位置开始到指定位置结束截取字符串。

### 常见对象(字符串的遍历)(掌握)
* A:案例演示
	* 需求：遍历字符串
```java
String s = "abcdef";
for(int i = 0; i < s.length(); i++) {			//通过for循环获取到字符串中每个字符的索引
	System.out.println(s.charAt(i));			//通过索引获取每一个字符
}
```

###12.10_常见对象(统计不同类型字符个数)(掌握)
* A:案例演示
	* 需求：统计一个字符串中大写字母字符，小写字母字符，数字字符出现的次数,其他字符出现的次数。
	* ABCDEabcd123456!@#$%^

```java
String s = "ABCDEabcd123456!@#$%^";
int big = 0;
int small = 0;
int num = 0;
int other = 0;
//1,获取每一个字符,通过for循环遍历
for(int i = 0; i < s.length(); i++) {
	char c = s.charAt(i);						//通过索引获取每一个字符
	//2,判断字符是否在这个范围内
	if(c >= 'A' && c <= 'Z') {
		big++;									//如果满足是大写字母,就让其对应的变量自增
	}else if(c >= 'a' && c <= 'z') {
		small++;
	}else if(c >= '0' && c <= '9') {
		num++;
	}else {
		other++;
	}
}

//3,打印每一个计数器的结果
System.out.println(s + "中大写字母有:" + big + "个,小写字母有:" + small + "个,数字字符:"
+ num + "个,其他字符:" + other + "个");
```

### 常见对象(String类的转换功能)(掌握)
* A:String的转换功能：
	* byte[] getBytes():把字符串转换为字节数组。
	* char[] toCharArray():把字符串转换为字符数组。
	* static String valueOf(char[] chs):把字符数组转成字符串。
	* static String valueOf(int i):把int类型的数据转成字符串。
		* 注意：String类的valueOf方法可以把任意类型的数据转成字符串

	* String toLowerCase():把字符串转成小写。(了解)
	* String toUpperCase():把字符串转成大写。
	* String concat(String str):把字符串拼接。

### 常见对象(按要求转换字符)(链式编程掌握)
* A:案例演示
	* 需求：把一个字符串的首字母转成大写，其余为小写。(只考虑英文大小写字母字符)

```java
String s = "woaiHEImaniaima";
String s2 = s.substring(0, 1).toUpperCase().concat(s.substring(1).toLowerCase());
System.out.println(s2);
```

### 常见对象(把数组转成字符串)
* A:案例演示
	* 需求：把数组中的数据按照指定个格式拼接成一个字符串
		* 举例：
			* int[] arr = {1,2,3};
		* 输出结果：
			* "[1, 2, 3]"

```java
int[] arr = {1,2,3};
String s = "[";							//定义一个字符串用来与数组中元素拼接

for (int i = 0; i < arr.length; i++) {	//{1,2,3}
	if(i == arr.length - 1) {
		s = s + arr[i] + "]";			//[1, 2, 3]
	}else {
		s = s + arr[i] + ", ";			//[1, 2,
	}
}
System.out.println(s);

```
### 常见对象(String类的其他功能)

* A:String的替换功能及案例演示
	* String replace(char old,char new)
	* String replace(String old,String new)
* B:String的去除字符串两空格及案例演示
	* String trim()
* C:String的按字典顺序比较两个字符串及案例演示
	* int compareTo(String str)(暂时不用掌握)
	* int compareToIgnoreCase(String str)(了解)


### 常见对象(字符串反转)
* A:案例演示
	* 需求：把字符串反转
		* 举例：键盘录入"abc"		
		* 输出结果："cba"

```java
Scanner sc = new Scanner(System.in);				//创建键盘录入对象
System.out.println("请输入一个字符串:");
String line = sc.nextLine();						//将键盘录入的字符串存储在line中

char[] arr = line.toCharArray();					//将字符串转换为字符数组

String s = "";
for(int i = arr.length-1; i >= 0; i--) {			//倒着遍历字符数组
	s = s + arr[i];									//拼接成字符串
}

System.out.println(s);
```

### 常见对象(在大串中查找小串出现的次数代码实现)
* A:案例演示
	* 统计大串中小串出现的次数

```java
//定义大串
String max = "woaiheima,heimabutongyubaima,wulunheimahaishibaima,zhaodaogongzuojiushihaoma";
//定义小串
String min = "heima";

//定义计数器变量
int count = 0;
//定义索引
int index = 0;
//定义循环,判断小串是否在大串中出现
while((index = max.indexOf(min)) != -1) {
	count++;									//计数器自增
	max = max.substring(index + min.length());
}

System.out.println(count);
```
