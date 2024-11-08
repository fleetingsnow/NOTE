## [主页](../README.md)/[Java](./readme.md)/代码笔记

### 整数类型

|关键字|取值范围|
|:----:|:----|
|byte|（-128~127）|
|short|（-32768~32767）|
|int|（-2147483648~2147483647）|
|long|（-9223372036854775808~9223372036854775807）|

**注意**：对于long型值，若赋给的值大于int型的最大值或小于int型的最小值，则需要在数字后加L或l，表示该数值为长整数，如long num = 2147483650L。

### 浮点类型

|关键字|取值范围|
|:----:|:----|
|float|1.4E-45~3.4028235E38|
|double|4.9E-324~1.7976931348623157E308|

**注意**:在默认情况下，小数都被看作double型，若使用float型小数，则需要在小数
后面添加F或f。可以使用后缀d或D来明确表明这是一个double类型数据，不加d不
会出错，但声明float型变量时如果不加f，系统会认为变量是double类型，从而出
错。

### 比较运算符
![](pic/Prolan5.png)

### 变量范围
1. **成员变量**
**定义**：在类体中所定义的变量被称为成员变量，成员变量在整个类中都有效。类的成
员变量又可分为两种，即静态变量和实例变量。
2. **局部变量**
**定义**：在类的方法体中定义的变量（方法内部定义，“{”与“}”之间的代码中声明
的变量）称为局部变量。局部变量只在当前代码块中有效。

### 字符类型
1.  **char型**
在定义字符型变量时，要以单引号表示，如's'表示一个字符，而"s"则表示一个字符
串，虽然只有一个字符，但由于使用双引号，它仍然表示字符串，而不是字符。
2. **转义字符**
转义字符是一种特殊的字符变量，它以反斜杠“\”开头，后跟一个或多个字符。
![](pic/Prolan1.png)

### 布尔类型（逻辑类型）
**关键字**：boolean
只有true和false两个值，分别代表布尔逻辑中的“真”和“假”。
**逻辑运算符**：![](pic/Prolan3.png)
**运算符的判定**：![](pic/Prolan4.png)
![](pic/Prolan2.png)

### 代码注释
1. **单行注释**
“//”为单行注释标记，从符号“//”开始直到换行为止的所有内容均作为注
释而被编译器忽略。
**语法**：//注释内容
2. **多行注释**
“/* */”为多行注释标记，符号“/*”与“*/”之间的所有内容均为注释内
容。注释中的内容可以换行。
**语法**：/* 注释内容1 注释内容2 … */
**注意**：
在多行注释中可嵌套单行注释。例如：
/* 程序名称：Hello world //开发时间：2008-03-05 */
注意
但在多行注释中不可以嵌套多行注释，以下代码为非法：
/* 程序名称：Hello world /*开发时间：2008-03-05 作者：张先生 */ */
3. 文档注释
“/** */”为文档注释标记。符号“/**”与“*/”之间的内容均为文档注释
内容。当文档注释出现在声明（如类的声明、类的成员变量的声明、类的成员方法
声明等）之前时，会被Javadoc文档工具读取作为Javadoc文档内容。文档注释的格
式与多行注释的格式相同。对于初学者而言，文档注释并不是很重要，了解即可。

### 循环控制
1. **if语句**
![](pic/Prolan6.png)
1. **if…else语句**
![](pic/Prolan7.png)
3. **if…else if多分支语句**
![](pic/Prolan8.png)
4. **switch多分支语句**
![](pic/Prolan9.png)
![](pic/Prolan10.png)
5. **while循环语句**
![](pic/Prolan11.png)
6. **do…while循环语句**
![](pic/Prolan12.png)
![](pic/Prolan13.png)
7. **for循环语句**
![](pic/Prolan14.png)

### 字符串
1. **连接多个字符串**
使用“+”运算符可实现连接多个字符串的功能。“+”运算符可以连接多个运
算符并产生一个String对象。
2. **获取字符串长度**
`String str = "We are students"; int size = str.length();`
上段代码是将字符串str的长度赋值给int型变量size，此时变量size的值为
这表示length()方法返回的字符串的长度包括字符串中的空格。

### 数组
1. **数组初始化**
一维数组：`int arr = new int{1,2,5,7}`
二维数组：`type arr[][]={15,23,48,59}`

2. **遍历数组**
**一维**：`for(数据类型 变量名:要遍历的数组)`  

**二维**：遍历二维数组需使用双层for循环，通过数组的length属性可获得数组的长
度
`int[][] b=new int[][]{}`
`for(int i=0;i<b.length;i++){`
   `for(int j=0;j<b.length;j++){`
   输出结果

3. **填充数组**
`fill(int[] a,int value)`
a：要进行元素替换的数组。
value：要存储数组中所有元素的值。
**指定范围**：
`fill(int[] a,int fromIndex,int toIndex,int value)`
a：要进行填充的数组。
fromIndex：要使用指定值填充的第一个元素的索引（包括）。
toIndex：要使用指定值填充的最后一个元素的索引（不包括）。
value：要存储在数组所有元素中的值。

4. **数组排序**
`Arrays.sort(object)`
object是指进行排序的数组名称。
5. **数组复制**
   1. copyOf()方法：
   `copyOf(arr,int newlength)`
   arr：要进行复制的数组。
newlength：int型常量，指复制后的新数组的长度。如果新数组的长度大
于数组arr的长度，则用0填充（根据复制数组的类型来决定填充的值，整型数组用0
填充，char型数组则使用null来填充）；如果复制后的数组长度小于数组arr的长
度，则会从数组arr的第一个元素开始截取至满足新数组长度为止。
    2. copyOfRange()方法:
    `copyOfRange(arr,int formIndex,int toIndex)`
    arr：要进行复制的数组对象。
formIndex：指定开始复制数组的索引位置。formIndex必须在0至整个数
组的长度之间。新数组包括索引是formIndex的元素。
toIndex：要复制范围的最后索引位置。可大于数组arr的长度。新数组不
包括索引是toIndex的元素。

6. **数组查询**
   1. `binarySearch(Object[],Object key)`
   a：要搜索的数组。
key：要搜索的值。
   2. `binarySearch(Object[],int fromIndex,int toIndex,Object
key)
`
该方法在指定的范围内检索某一元素。
a：要进行检索的数组。
fromIndex：指定范围的开始处索引（包含）。
toIndex：指定范围的结束处索引（不包含）。
key：要搜索的元素。

### 对象和类
1. **抽象类**
抽象类一般指父类，指在该类中只给出该类的标准，没有给出具体的方法。
**例子**：图形类作为所有图形的父类，具有绘制图形的能
力，这个方法可以称为“绘制图形”，但如果要执行这个“绘制图形”的命令，没
有人知道应该画什么样的图形，并且如果要在图形类中抽象出一个图形对象，没有
人能说清这个图形究竟是什么图形，

2. **接口**

**例子**：接口的概念在现实中也极为常见，如从不同的五金商店买来
螺丝帽和螺丝钉，螺丝帽很轻松地就可以拧在螺丝钉上，可能螺丝帽和螺丝钉的厂
家不同，但这两个物品可以轻易地组合在一起，这是因为生产螺丝帽和螺丝钉的厂
家都遵循着一个标准，这个标准在Java中就是接口。

3. **权限修饰符**
![](pic/Prolan15.png)

4. **对象比较**
Java中有两种比较方式“==”和`equals`
![](pic/Prolan16.png)
![](pic/Prolan17.png)
从上述运行结果中可以看出，“==”运算符和equals()方法比较的内容是不相
同的，equals()方法是String类中的方法，它用于比较两个对象引用所指的内容是
否相等；而“==”运算符比较的是两个对象引用的地址是否相等。由于c1与c2是两
个不同的对象引用，两者在内存中的位置不同，而“String c3=c1;”语句将c1的
引用赋给c3，所以c1与c3这两个对象引用是相等的，也就是打印c1==c3这样的语句
将返回true值。
**c1,c2,c3的内存分布**
![](pic/Prolan18.png)

### 包装类
#### Integer类
**Integer类的常用方法**：
![](pic/Prolan19.png)
Integer类提供了以下4个**常量**。
`MAX_VALUE`：表示int类型可取的最大值，即2
31-1。
`MIN_VALUE`：表示int类型可取的最小值，即-2
31。
`SIZE`：用来以二进制补码形式表示int值的位数。
`TYPE`：表示基本类型int的Class实例。

#### Boolean类
**Boolean类的常用方法**
![](pic/Prolan20.png)

#### Byte类
**Byte类常用方法**
![](pic/Prolan21.png)
**常量：**
`MIN_VALUE`：byte类型可取的最小值。
`MAX_VALUE`：byte类型可取的最大值。
`SIZE`：用于以二进制补码形式表示byte值的位数。
`TYPE`：表示基本类型byte的Class实例。

#### Character类
**Character类常用方法**
![](pic/Prolan22.png)

#### Double类
**Double类常用方法**
![](pic/Prolan23.png)
**常量**
`MAX_EXPONENT`：返回int值，表示有限double变量可能具有的最大指数。
`MIN_EXPONENT`：返回int值，表示标准化double变量可能具有的最小指
数。
`NEGATIVE_INFINITY`：返回double值，表示保存double类型的负无穷大值
的常量。
`POSITIVE_INFINITY`：返回double值，表示保存double类型的正无穷大值
的常量。

### 数字格式化
**特殊字符**：![](pic/Prolan24.png)

### 取整函数
1. `public static double ceil(double a)`：返回大于等于参数的最小整
数。
2. `public static double floor(double a)`：返回小于等于参数的最大整
数。
3. `public static double rint(double a)`：返回与参数最接近的整数，
如果两个同为整数且同样接近，则结果取偶数。
4. `public static int round(float a)`：将参数加上0.5后返回与参数最
近的整数。
5. `public static long round(double a)`：将参数加上0.5后返回与参数
最近的整数，然后强制转换为长整型。

### 取最大值、最小值、绝对值函数方法
1. `public static double max(double a,double b)`：取a与b之间的最大
值。
2. `public static int min(int a,int b)`：取a与b之间的最小值，参数为
整型。
3. `public static long min(long a,long b)`：取a与b之间的最小值，参
数为长整型。
4. `public static float min(float a,float b)`：取a与b之间的最小
值，参数为浮点型。
5. `public static double min(double a,double b)`：取a与b之间的最小
值，参数为双精度型。
5. `public static int abs(int a)`：返回整型参数的绝对值。
6. `public static long abs(long a)`：返回长整型参数的绝对值。
7. `public static float abs(float a)`：返回浮点型参数的绝对值。
8. `public static double abs(double a)`：返回双精度型参数的绝对值。

### 随机数
#### `Math.random()`类
![](pic/Prolan25.png)
此方法同样可以用于生成随机字符

#### `Random()`类
`Random r=new Random()`(实例化一个Random类)
若想不生成同样的随机数，可以在实例化Random类时设置随机数种子，语法如下：
`Random r=new Random(seedValue)`
**常用方法：**
`public int nextInt()`：返回一个随机整数。
`public int nextInt(int n)`：返回大于等于0且小于n的随机整数。
`public long nextLong()`：返回一个随机长整型值。
`public boolean nextBoolean()`：返回一个随机布尔型值。
`public float nextFloat()`：返回一个随机浮点型值。
`public double nextDouble()`：返回一个随机双精度型值。
`public double nextGaussian()`：返回一个概率密度为高斯分布的双精
度值。

### 大数字运算
#### `BigInteger`
实例化BigInteger类语法：
`public BigInteger(String val)`
**其中val是十进制字符串，所以双引号不能省略**
运算方法：
1. `public BigInteger add(BigInteger val)`：做加法运算。
2. `public BigInteger subtract(BigInteger val)`：做减法运算。
3. `public BigInteger multiply(BigInteger val)`：做乘法运算。
4. `public BigInteger divide(BigInteger val)`：做除法运算。
5. `public BigInteger remainder(BigInteger val)`：做取余操作。
6. `public BigInteger[] divideAndRemainder(BigInteger val)`：用数
组返回余数和商，结果数组中第一个值为商，第二个值为余数。
7. `public BigInteger pow(int exponent)`：进行取参数的exponent次方
操作。
8. `public BigInteger negate()`：取相反数。
9. `public BigInteger shiftLeft(int n)`：将数字左移n位，如果n为负
数，做右移操作。
10. `public BigInteger shiftRight(int n)`：将数字右移n位，如果n为负
数，做左移操作。
11. `public BigInteger and(BigInteger val)`：做与操作。
12. `public BigInteger or(BigInteger val)`：做或操作。
13. `public int compareTo(BigInteger val)`：做数字比较操作。
13. `public boolean equals(Object x)`：当参数x是BigInteger类型的数
字并且数值相等时，返回true。
14. `public BigInteger min(BigInteger val)`：返回较小的数值。
15. `public BigInteger max(BigInteger val)`：返回较大的数值。

#### `BigDecimal`
两种构造方法：
1. `public BigDecimal(double val)`：实例化时将双精度型转换为BigDecimal类型。
2. `public BigDecimal(String val)`：实例化时将字符串形式转换为BigDecimal类型。

#### 运算方法
1. `public BigDecimal add(BigDecimal augend)`：做加法操作。
2. `public BigDecimal subtract(BigDecimal subtrahend)`：做减法操
作。
3. `public BigDecimal multiply(BigDecimal multiplicand)`：做乘法
操作。
4. `public BigDecimal divide(BigDecimal divisor,int scale,int
roundingMode)`：做除法操作，方法中3个参数分别代表除数、商的小数点后的位
数、近似处理模式。
**divide方法的多种设置方式
![](pic/Prolan26.png)

### Object类
主要方法：
1. getClass()方法
getClass()方法是Object类定义的方法，它会返回对象执行时的Class实例，
然后使用此实例调用getName()方法可以取得类的名称。
2. toString()方法
toString()方法的功能是将一个对象返回为字符串形式，它会返回一个String
实例。在实际的应用中通常重写toString()方法，为对象提供一个特定的输出模
式。当这个类转换为字符串或与字符串连接时，将自动调用重写的toString()方
法。
3. equals()方法
“==”比较的是两个对象的引用是否相等，而equals()方法比较的是两个对象的实际内容。来看下面的实例。

###　使用instanceof操作符判断对象类型
判断父类对象是否为子类对象的实例。这个判断通常使用instanceof操作符来完成。
**语法如下：**
`myobject instanceof ExampleClass`
myobject：某类的对象引用(子类)。
ExampleClass：某个类(父类)。

### final型变量常用方法
![](pic/Prolan27.png)
### final方法
final方法不能被重写
### 异常捕捉
Java语言的异常捕获结构由try、catch和finally 3部分组成。其中，try语句块存放的是可能发生异常的Java语句；catch程序块在try语句块之后，用来激发被捕获的异常；finally语句块是异常处理结构的最后执行部分，无论try语句块中的代码如何退出，都将执行finally语句块
1.**try-catch语句块** 
当try代码块中的语句发生异常时，程序就会调转到catch代码块中执行，执行完catch代码块中的程序代码后，将继续执行catch代码块后的其他代码，而不会执行try代码块中发生异常语句后面的代码。
2. **finally语句块**
完整的异常处理语句一定要包含finally语句，无论程序中有无异常发生，并且无论之间的try-catch是否顺利执行完毕，都会执行finally语句。
**注意：**
在以下4种特殊情况下，finally块不会被执行：
1. 在finally语句块中发生了异常。
2. 在前面的代码中使用了System.exit()退出程序。
3. 程序所在的线程死亡。
4. 关闭CPU。
**java中常见异常**
![](pic/Prolan28.png)

### 运行时程序错误
![](pic/Prolan29.png)