## 介绍
此文档主要介绍 Javascript 的编码规范以及基本风格要求。

## 版本要求
最低 JS 版本是 ES5, 尽量以 ES6（即 ES2015）规范来编写代码，因为我们会使用 babel 做兼容转译。

## 检测工具
使用 [ESLint](https://eslint.org/) 进行检查，基于 [eslint-config-bitpower](https://github.com/bitpower-frontend/eslint-config-bitpower) 配置。

## 具体规范

### 语言规范
---
1.&nbsp;**尽量** 使用字面量方式创建对象、数组等其他复合数据类型。
```js
const obj = {};
const arr = [];
```

---
2.&nbsp;**推荐** 使用字符串模板的方式进行字符串与变量的连接。
```js
const name = 'Hisheng';
console.log(`my name is ${name}`);
```

---
3.&nbsp;除非你很懂 prototype，否则 **尽量** 使用 class 替代原型继承。

---
4.&nbsp;数组循环时，**推荐** 提前对数组长度做求值缓存。
```js
for(let i=0, ilen=arr.length; i<ilen; i++){
  //
}
```

---
5.&nbsp;**不要** 尝试修改内置对象原型。

---
6.&nbsp;**尽量** 使用 `const` 和 `let` 替代 `var` 命名变量。（注意三者使用区别）

### 代码风格规范

---
1.&nbsp;**必须** 使用两个空格进行代码缩进。（IDE 设置 tab 用两个空格代替）

---
2.&nbsp;大括号缩进 **必须** 使用 `One True Brace Style` 风格。
* One True Brace Style

```js
if (foo) {
  bar();
} else {
  baz();
}
```
* Stroustrup

```js
if (foo) {
  bar();
}
else {
  baz();
}
```
* Allman

```js
if (foo)
{
  bar();
}
else
{
  baz();
}
```

---
3.&nbsp;变量命名

  1.&nbsp;一般变量命名 **必须** 使用驼峰命名法。

  2.&nbsp;类或者构造函数的命名 **必须** 使用驼峰命名法且首字母大写。


---
4.&nbsp;代码之间最大空行数为 2。
```js
const a = 1;
// blank line 1
// blank line 2
const b = 2;
// blank line 1
const c = 3;
```


---

5.&nbsp;关于逗号的使用

1.&nbsp;单行对象字面量最后属性 **不要** 以逗号结尾

```js
// 推荐
const obj = { x: 1, y: 2 };
// 不推荐
const obj = { x: 1, y: 2, };
```
2.&nbsp;多行对象字面量最后属性 **推荐** 以逗号结尾

```js
// 推荐
const obj = {
  x: 1,
  y: 2,
};
// 不推荐
const obj = {
  x: 1,
  y: 2
};
```
3.&nbsp;函数参数最后声明的参数 **不要** 以逗号结尾

```js
// 推荐
function test(a, b){
  //
}
// 不推荐
function test(a, b,){
  //
}
```
4.&nbsp;函数调用时传入最后参数 **不要** 以逗号结尾

```js
// 推荐
test(a, b);
// 不推荐
test(a, b,);
```

---
6.&nbsp;关于空格的使用

1.&nbsp;对象属性，数组元素之间 **必须** 以 **单个** 空格隔开

```js
// 推荐
const obj = { x: 1, y: 2 };
const arr = [1, 2, 3];
// 不推荐
const obj = { x: 1,y: 2 };
const arr = [1,2,3];
```

2.&nbsp;对象属性 `key` 与 `value` 之间的冒号之前不留空格，之后留 **单个** 空格

```js
// 推荐
const obj = { x: 1, y: 2 };
// 不推荐
const obj = { x:1, y:2 };
const obj = { x : 1, y : 2 };
```

3.&nbsp;对象字面量声明花括号与属性之间 **必须** 以 **单个** 空格隔开

```js
// 推荐
const obj = { x: 1, y: 2 };
// 不推荐
const obj = {x: 1, y: 2};
```

4.&nbsp;函数声明参数与函数调用传参之间 **必须** 以 **单个** 空格隔开

```js
// 推荐
function test(a, b){
  //
}
test(a, b);
// 不推荐
function test(a,b){
  //
}
test(a,b);
```

5.&nbsp;操作符前后 **必须** 添加空格。
```js
const a = 1 + 1;
const b = a / 2;
```

---
7.&nbsp;关于分号的使用

1.&nbsp;所有语句 **必须** 以分号结尾
```js
// 推荐
console.log('hello, world');
// 不推荐
console.log('hello, world')
```

2.&nbsp;函数、类的声明 **不需要** 以分号结尾
```js
// 推荐
function test(){
  //
}
class User {
  //
}
// 不推荐
function test(){
  //
};
class User {
  //
};
```
**但是**，以变量声明方式定义的函数则依然保持分号结尾不变

```js
const test = function(){
  //
};
```

---
8.&nbsp;关于单引号与双引号的使用

1.&nbsp;所有对字符串的操作以赋值 **推荐** 使用单引号
```js
// 推荐
const name = 'bitpower';
console.log('hello, world');
// 不推荐
const name = "bitpower";
console.log("hello, world")
```