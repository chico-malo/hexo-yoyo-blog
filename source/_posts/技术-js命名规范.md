---
title: '[技术]-js命名规范'
date: 2020-06-12 10:20:58
tags:
  - 技术
  - javaScript
top: true
cover: false
summary: javaScript命名规范
categories: 技术
---

# js命名规范
`前端技术太多，不可能熟悉每一个知识点，熟知其核心尽快上手，需要用时再翻看api文档。`
`“敲出每一行完美的代码，默默的改变这个世界！”`

------
规范大部分取自于[简书-小母鸡叽叽叽](https://www.jianshu.com/p/75591d47312a)

------



## 一、变量

命名方法:  小驼峰式命名法
命名规范：前缀为形容词 （函数前缀为动词, 以此来区分函数和变量）

```javascript
// 好的命名方式
let maxCount = 10;
let tableTitle = '啦啦啦';
```



------



## 二、常量

命名方法：名词全部大写
命名规范：使用大写字母和下划线来组合命名，下划线用来分割单词。

```javascript
const MAX_COUNT = 10;
const URL = '//www.huifenqi.com';
```



------



## 三、函数 & 方法

命名方法： 小驼峰式命名法
命名规范： 前缀应该为动词
命名建议：常用动词约定

```
动词	含义
can	判断是否可执行某个动作
has	判断是否含义某个值
is	判断是否为某个值
get	获取某个值
set	设置某个值
load	加载某些数据
// 是否可阅读
function canRead() {}
// 获取名称
function getName() {}
```



------



## 四、类 & 构造函数

命名方法：大写驼峰式命名法，首字母大写。
命名规范：前缀为名称。

```javascript
class Persion {
  constructor(name) {
   ...
  }
}

let person = new Person('啦啦啦');
```



------



## 五、类的成员

类的成员包括：

公共属性和方法： 跟变量和函数命名一样。
私有属性和方法：前缀为下划线_, 后面跟公共属性和方法一样的命名方式。

```javascript
class Person {
  // 私有属性 
  _name: string;
  constructor() { }

  // 公共方法
  getName() {
    return this._name;
  }
  // 公共方法
  setName(name) {
    this._name = name;
  }
}
```



------



## 六、注释规范

```javascript
// 单行注释

// 函数方法注释 —— webStorm快捷键/* + 回车
/**
 * 函数说明
 * @关键字
 **/
```


