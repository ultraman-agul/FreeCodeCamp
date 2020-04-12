## JavaScript 基础

对象属性名带有空格时，引用必须使用中括号：

```js
var mydog={
"my name" : "wangcai",
"legs" : 4,
 "tails" : 1
}
var hi = mydog["my name"];
var feet = mydog.legs;
```

当我们通过变量名访问属性的时候，不需要给变量名包裹引号。因为实际上我们使用的是变量的值，而不是变量的名称。

给`myDog`添加一个`"bark"`属性，设置它的值为狗的声音，例如："woof"。下面代码如果对象不存在`bark`属性则新建属性赋值，已经存在则修改值。

```javascript
myDog.bark = "woof";
或
myDog["bark"] = "woof";
```

从`myDog`中删除`"tails"`属性

```js
delete myDog.tails;
```

先后顺序

```javascript
function phoneticLookup(val) {
var result = "";
var lookup = {
  "alpha" : "Adams",
  "bravo" : "Boston",
  "charlie" : "Chicago",
  "delta" : "Denver",
  "echo" : "Easy",
  "foxtrot" :"Frank"
};
result = lookup[val]; //调用对象语句必须要在对象语句后面，否则无法调用
  return result;
}
phoneticLookup("charlie");
```

有时检查一个对象属性是否存在是非常有用的，我们可以用`.hasOwnProperty(propname)`方法来检查对象是否有该属性。如果有返回`true`，反之返回`false`。

对象将数据以一种键-值对的形式保存。在上面的示例中，`"artist": "Daft Punk"`是一个具有`"artist"`键和`"Daft Punk"`值的属性。

[JavaScript Object Notation](http://www.json.org/) 简称`JSON`是用于存储数据的相关数据交换格式。数组中有多个 JSON 对象的时候，对象与对象之间要用逗号隔开。

与访问嵌套对象一样，用中括号操作符同样可以访问嵌套数组。嵌套对象和嵌套数组可以灵活使用**中括号操作符[]和点操作符.**进行访问。

```js
Math.random() //返回一个0~1的随机小数，可能为0，不可能为1
```

生成随机整数：
`Math.random()`生成一个随机小数。
把这个随机小数乘以20。
用`Math.floor()`向下取整 获得它最近的整数。

返回范围内随机整数

```js
Math.floor(Math.random() * (max - min + 1)) + min  //包含max和min
```



`parseInt()`函数解析一个字符串并返回一个整数。它同时可接受第二个参数，一个介于2和36之间的整数，表示字符串的基数。

函数调用如下所示：

```
parseInt(string, radix);
```

示例：

```
var a = parseInt("11", 2);
```

参数 2 表示 "11" 使用二进制数值系统。此示例将字符串 "11" 转换为整数 3。