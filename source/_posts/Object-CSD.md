---
cover: https://fristnamecao.github.io/img/imgs/0_7.jpg
title: Object_CSD
date: 2023-02-12 14:16:32
---

# 数据及结构与对象

Math[PI] 

此种语法，中括号里面是一个表达式 表达式计算结果应该是一个字符串 该字符串被当做要读取的属性的名 整个表达式返回该属性的属性值  

Math["PI"]

Math['P'+'I']

x="PI"

Math[x]

是可以的



// 数组是值的“有序”集合

 // 对象是值的“具名”集合 

// 在数组中，我们为值编号 

// 在对象中，我们为值起名 

// 有些语言里，对象又叫关联数组 

//   把值与名字“关联”起来 



JS中一切皆对象（除空值以外）

因为一切都能读出属性

因为对于任何一个值来说，以下表达式都不报错

在其它很多语言里，能读出属性的只有对象

从能否可再拆分的角度讲，原始类型不算对象

但从能否读取属性的角度讲，原始类型也算对象，因为它们能读出属性

x = 2

x.toFixed()

y = 'owiejfo'

y.length

y.toUpperCase()

z = true

z.toString()





> c== a//相等运算判断对象时，返回的是两边是否是同一个对象
> //而判断原始类型时工返回的是两边的值是否相同



为了找出对象具有的属性，可以使用 Object.keys 函数。 

你给它一个对象，它返回一个字符 

串数组 - 对象的属性名称

console.log(Object.keys({x: 0, y: 0, z: 2})); 

// → ["x", "y", "z"]



**Object.assign（）** 方法将所有[可枚举](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/propertyIsEnumerable)（ 返回 true）和[自有](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)（ 返回 true）属性从一个或多个源对象复制到目标对象，返回修改后的对象。 

实列一

let objectA = {a: 1, b: 2}; 

Object.assign(objectA, {b: 3, c: 4}); 

console.log(objectA); 

// → {a: 1, b: 3, c: 4} 



实列二

const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };

const returnedTarget = Object.assign(target, source);

console.log(target);
// expected output: Object { a: 1, b: 4, c: 5 }

console.log(returnedTarget);
// expected output: Object { a: 1, b: 4, c: 5 }



copyWithin（0，3，6）将3-6复制到前面







