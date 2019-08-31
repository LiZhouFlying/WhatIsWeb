# WhatIsWeb
2019前端学习之路

#8月31日
- 对象
 #### 1.简单基本类型和对象子类的内置函数的差别
 以字符串为例，string是简单基本类型而String是内置函数，简单基本类型必须转换成对象才能获得如长度length或者其中的某个字符，这一步在有必要时语言会自动将字符串字面量转换成一个对象，所以不需要对基本类型使用如toString()的操作
 #### 2.获取字符串String的长度
 有两种方式: stringValue[2] 和 stringValue.charAt(2)
 差别: 在下标超出字符串长度时前者返回undefined，后者会返回一个空格
 #### 3.控制number类型的小数点后位数
 对于浮点数而言可以使用toFixed(【位数】)来控制小数点后的位数，需要注意:Dobule的精度是小数点后15位，所以当【位数】> 15时，会出现非0值
 #### 4.为数组添加内容还是属性
 数组也是对象，能当做一个普通的键/值对象使用，所以特别需要注意添加的是属性还是内容
 arrayValue.baz = "value”;  —>添加了一个属性，length = 3
 arrayValue[arrayValue.length] = 67;  —>添加了内容
 arrayValue[“3"] = 67; —> 属性名看起来像一个数字时，就会变成一个数值下标，所以length = 4
 #### 5.属性描述符的使用
 writable:是否可修改该属性的值
 当该属性的值为false时，在非严格模式下修改会静默失败，而在严格模式(”use strict“)下会直接抛出typeError:
 TypeError: Cannot assign to read only property 'b' of object '#<Object>'
 特别需要注意的是: 在设置setter和getter方法时，不能同时设置writable属性！！会直接抛出TypeError:
 TypeError: Invalid property descriptor. Cannot both specify accessors and a value or writable attribute,
  
 configurable:是否可配置该属性
 当设置该属性值为false时，不管是否处于严格模式，试图修改一个不可配置的属性描述符都会出错的，同时也无法删除对象中该值 delete myObject.a 。可以把
 writable状态从true变成false，但是无法由false改为true.
 特别需要注意的是: 如果修改一个对象的configurable = false时，是可以修改该对象下的属性值！！
 
