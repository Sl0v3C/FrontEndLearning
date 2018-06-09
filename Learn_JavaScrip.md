# Learning the JavaScript

## JavaScript Grammar
### JavaScript变量
变量必须以字母开头  
也能以$和_开头，但是不推荐这样做  
变量名对大小写敏感  
<pre>
    var x=2;
    var y=3;
    var z=x+y
</pre>

一条语句声明多个变量：
<pre>
    var name="PYY", age=32, gender="male",
    phone=13800000000; //可跨行
</pre>
未使用值来声明的变量，其值实际上是undefined:
<pre>
    var name;
</pre>
重新声明变量，其原来的值不会丢失：
<pre>
    var name="PYY";
    var name; // name still is "PYY"
</pre>

### JavaScript数据类型  
JavaScript拥有动态类型，相同的变量可用作不同的类型:  

    var x；
    var x=6；
    var x="Bill"

字符串：是存储字符的变量，可以是单引号或双引号中的任意文本：  

    var name='PYY';
    var string="I love 'HJ'!"

数字：数字可以带小数或者不带，极大或极小的数字可以通过科学(指数)计数来书写：  

    var x1=34.00;
    var x2=101;
    var x3=123e5; // 12300000
    var x4=123e-5 // 0.00123

布尔：只能有两个值，true或false：

    var TRUE=true;
    var FALSE=false;

数组：可以通过Array()构造数组。可以分别初始化下标或者直接调用Array()构造函数初始化;或者直接通过[]初始化：

    var cars=new Array();
    cars[0]='Audi';
    cars[1]='BMW';
    cars[2]='Volvo';
    或
    var cars=new Array('Audi', 'BMW', 'Volvo');
    或
    var cars=['Audi','BMW','Volvo'];

对象：对象由花括号分隔。在括号内部，对象的属性以名称和值对的形式(name : value)来定义。属性之间由逗号分隔：  

    var person={
        firstname : "Yangyi",
        lastname : "Peng",
        id : 1010
    };
    对象有两种获取属性的方式:
    lastname=person.lastname
    lastname=person["lastname"]

undefined和null:undefined这个值表示变量不含有值。  
可以通过将变量的值设置为null来清空变量。  

    person=null;  // 清空上文的person对象

声明变量类型：声明新变量时，可以使用关键词"new"来声明其类型：  

    var carname=new String;
    var x=new Number;
    var y=new Boolean;
    var cars=new Array;
    var person=new Object;
JS变量均为对象。当声明一个变量时，就创建了一个新的对象。

### JS对象
JS中所有的事物都是对象：字符串、数字、数组、日期等(这点和Python一样)。对象是拥有属性和方法的数据。

    var string='Hello World!'
实际上上面创建了一个JS字符串对象。  
字符串对象拥有内建的属性length以及若干个内建的方法：  

    string.length  // 12
    string.indexOf()
    string.replace()
    string.search()
属性和方法常被称为对象的成员。
    person=new Object();
    person.firstname="Yangyi";
    person.lastname="Peng";
    person.age=32;
在面向对象的语言中，使用camel-case标记法的函数是很常见的。类似someMethod().

### JS函数
函数是由事件驱动的或者当它被调用时执行的可重复使用的代码块。  
语法：

    function func(arg1, arg2, ...):
    {
        do something;
        return something;
    }
JS对大小写敏感。  

#### JS局部变量
JS函数内部声明的变量(使用var)是局部变量，所以只能在函数内部访问它，作用域是局部的。函数运行以后被删除。

#### JS全局变量
在函数外声明的变量，网页上的所有脚本和函数都能访问它。全局变量会在页面关闭后被删除。  
如果把值赋给尚未声明的变量，该变量将被自动作为全局变量声明。

### JS运算符
#### 算术运算符
    +   加
    -   减
    *   乘
    /   除
    %   求余数
    ++  累加
    --  递减

#### 赋值运算符
    =   变量赋值
    +=  x+=y  --> x=x+y
    -=  x-=y  --> x=x-y
    *=  x*=y  --> x=x*y
    /=  x/=y  --> x=x/y
    %=  x%=y  --> x=x%y
用于字符串的+运算符：+运算符用于把文本值或字符串变量连接起来。  
如果把数字与字符串相加，结果将成为字符串。

#### 比较运算符
    ==  等于
    === 全等(值和类型)
    !=  不等于
    >   大于
    <   小于
    >=  大于或等于
    <=  小于或等于

#### 逻辑运算符
    &&  逻辑与
    ||  逻辑或
    !   逻辑非

#### 条件运算符（三目）
    varible=(condition)?value1:value2

### JS条件语句
条件语句用于基于不同的条件来执行不同的动作。 

    if语句
    if (condition)
      {
      do someting;
      }
    if...else语句
    if...else if...else语句
    switch语句
    switch(cond)
      {
      case 1:
        do sth;
        break;
      case 2:
        do sth;
        break;
      ...
      default:
        do sth;
      }

### JS循环
#### for循环
    for (语句1; 语句2; 语句3)
    {
    do something;
    }

#### for/in循环
循环遍历对象的属性：

    var person={fname:"Yangyi", lname:"Peng",age:32};
    for (x in person)
      {
      do something;
      }

#### while循环
    while (condition)
      {
      do sth;
      }

#### do/while循环
该循环会先执行一次代码块，再检查条件是否为真。

    do
      {
      do sth;
      }
    while (cond)

### JS break和continue语句
break语句用于跳出循环; continue语句用于跳过循环中的一个迭代。  

### JS标签
continue语句(带标签或不带标签)只能用在循环中。  
break语句(不带标签)，只能用在循环或switch中。  
通过标签引用，break语句可用于跳出任何JS代码块。  

    cars=["Benz","Audi","Nissan","Honda"];
    list:
    {
    document.write(cars[0] + "<br>");
    document.write(cars[1] + "<br>");
    break list;
    document.write(cars[2] + "<br>");
    document.write(cars[3] + "<br>");
    }
    above only show Benz & Audi

### JS错误: throw, try, catch
try语句测试代码块的错误。  
catch语句处理错误。  
throw语句创建自定义错误。 

    try
      {
      do sth;
      }
    catch(err)
      {
      do sth;
      }
throw语句允许创建自定义错误。  
语法：throw exception  

    <script>
    function myFunction()
    {
    try
    { 
    var x=document.getElementById("demo").value;
    if(x=="")    throw "值为空";
    if(isNaN(x)) throw "不是数字";
    if(x>10)     throw "太大";
    if(x<5)      throw "太小";
    }
    catch(err)
    {
    var y=document.getElementById("mess");
    y.innerHTML="错误：" + err + "。";
    }
    }
    </script>

### JS表单验证
可用来在数据被送往服务器前对HTML表单中的这些输入数据进行验证。  
e.g.：
用户是否已填写表单中的必填项目：
    
    如果必填或必选为空，弹出警告框，返回false
    function validate_required(field,alerttxt)
    {
    with (field)
    {
    if (value==null||value=="")
    {alert(alerttxt);return false}
    else {return true}
    }
    }
e-mail验证：输入的数据必须包含@符号和点号(.)。同时@不可以是邮件地址的首字符，并且@之后需有至少一个点号：
    function validate_email(field,alerttxt)
    {
    with (field)
    {
    apos=value.indexOf("@")
    dotpos=value.lastIndexOf(".")
    if (apos<1||dotpos-apos<2) 
    {alert(alerttxt);return false}
    else {return true}
    }
    }

### JS HTML DOM
文档对象模型，当网页被加载时，浏览器会创建页面的文档对象模型。
<pre>
                    文档
                     |
                   根元素html
                     |
   |—————————————————————————————|
  元素head                      元素body
   |                             |
  元素title       属性href——元素a  元素h1
   |                        |       |
  文本"标题"            文本"链接"  文本"标题"
</pre>
#### 查找HTML元素
当通过JS操作HTML元素，必须先找到该元素：
* 通过id找到HTML元素  
    document.getElementById()  
    没找到返回null
* 通过标签名找到HTML元素  
    getElementsByTagName()
* 通过类名找到HTML元素  
    getElementsByClassName()

#### 改变HTML
HTML DOM允许JS改变HTML元素的内容。
JS中, document.write()可用于直接向HTML输出流写内容。绝不要在文档加载之后使用document.write()，会覆盖该文档。如：  
```
<!DOCTYPE html>
<html>
<script>
function tap ()
{
  document.write(Date());
}
</script>

<body>
<input type="button" id="btn" onclick="tap()" value="点我"/>
</body>
</html>
```
##### 改变HTML内容：
修改HTML内容的最简单的方法是使用innerHTML属性。  
    
    document.getElementById(id).innerHTML=new content
```
<html>
<body>

<p id="p1">Hello World!</p>

<script>
document.getElementById("p1").innerHTML="New text!";
</script>

</body>
</html>
```
##### 改变HTML属性
使用下面的语法修改HTML元素的属性：

    document.getElementById(id).attribute=new value

#### 改变CSS
HTML DOM允许JS改变HTML元素的样式。
使用下面语法改变HTML元素的样式：

    document.getElementById(id).style.property=new style
```
<!DOCTYPE html>
<html>
<body>

<p id="p1">Hello World!</p>
<p id="p2">Hello World!</p>

<script>
document.getElementById("p2").style.color="blue";
document.getElementById("p2").style.fontFamily="Arial";
document.getElementById("p2").style.fontSize="larger";
</script>

<p>上面的段落已被一段脚本修改。</p>

</body>
</html>

```

#### HTML DOM事件
HTML DOM使JS有能力对HTML事件做出反应。  
HTML事件的例子：

    当用户点击鼠标时；
    当网页已加载时；
    当图像已加载时；
    当鼠标移动到元素上时；
    当输入字段被改变时；
    当提交HTML表单时；
    当用户出发按键时；
```
onclick事件当按钮被点击时触发
onload在用户进入页面时触发。可用于检测访问者的浏览器类型和浏览器版本，并基于这些信息来加载网页的正确版本。
onunload在用户离开页面时触发。其与onload事件可用于处理cookie。
onchange事件常结合对输入字段的验证来使用。
onmouseover和onmouseout事件可用于在用户的鼠标移至HTML元素上方或移出元素时触发函数。
onmousedown, onmouseup事件。首先当点击鼠标按钮时，会触发onmousedown事件，当释放鼠标按钮时，会触发onmouseup事件。
onfocus事件用于当输入字段获得焦点时触发。

```

#### HTML DOM元素(节点)
添加节点：首先创建该元素，然后向一个已存在的元素追加该元素。
```
<div id="div1">
<p id="p1">这是一个段落</p>
<p id="p2">这是另一个段落</p>
</div>

<script>
// 创建了新的<p>元素
var para=document.createElement("p");
// 创建了文本节点
var node=document.createTextNode("这是新段落。");
// 向<p>元素追加这个文本节点
para.appendChild(node);
// 找到一个已有的元素
var element=document.getElementById("div1");
// 向这个已有的元素追加新元素
element.appendChild(para);
</script>
```

删除已有HTML元素：必须首先获得该元素的父元素，然后找到需要删除的元素，之后从父元素中删除该元素。
```
<div id="div1">
<p id="p1">这是一个段落。</p>
<p id="p2">这是另一个段落。</p>
</div>

<script>
// 获得p1的父元素div1
var parent=document.getElementById("div1");
// 获得需要删除的p1元素
var child=document.getElementById("p1");
// 从父元素中将p1元素删除
parent.removeChild(child);
</script>
```
通常可以找到需要删除的元素，然后通过其parentNode属性来找到父元素。
```
var child=document.getElementById("p1");
child.parentNode.removeChild(child);
```

### JS对象
JS中的所有事物都是对象:字符串，数值，数组，函数等。且JS允许自定义对象。
