# Hoisting
变量提升（Hoisting）被认为是， Javascript中执行上下文 （特别是创建和执行阶段）工作方式的一种认识。在 ECMAScript® 2015 Language Specification 之前的JavaScript文档中找不到变量提升（Hoisting）这个词。不过，需要注意的是，开始时，这个概念可能比较难理解，甚至恼人。

例如，从概念的字面意义上说，“变量提升”意味着变量和函数的声明会在物理层面移动到代码的最前面，但这么说并不准确。实际上变量和函数声明在代码里的位置是不会动的，而是在==编译==段被放入内存中。

## 技术范例
JavaScript 在执行任何代码段之前，将函数声明放入内存中的优点之一是，你可以在声明一个函数之前使用该函数。例如：

```javascript
/**
* 正确的方式：先声明函数，再调用函数 (最佳实践)
*/
function catName(name) {
    console.log("我的猫名叫 " + name);
}

catName("Tigger");

/*
以上代码的执行结果是: "我的猫名叫 Tigger"
*/
```

上面的代码片按照是你的正常思维（先声明，后调用）去书写的。现在，我们来看看当我们在写这个函数之前调用这个函数会发生什么：

```javascript
/**
* 不推荐的方式：先调用函数，再声明函数 
*/

catName("Chloe");

function catName(name) {
    console.log("我的猫名叫 " + name);
}

/*
代码执行的结果是: "我的猫名叫 Chloe"
*/
```

即使我们在定义这个函数之前调用它，函数仍然可以工作。这是因为在 JavaScript 中执行上下文的工作方式造成的。

变量提升也适用于其他数据类型和变量。变量可以在声明之前进行初始化和使用。但是如果没有初始化，就不能使用它们。

译者注： 函数和变量相比，会被优先提升。这意味着函数会被提升到更靠前的位置。

## 只有声明被提升
JavaScript only hoists declarations, not initializations. If a variable is declared and initialized after using it, the value will be undefined. For example:
```javascript
console.log(num); // Returns undefined 
var num;
num = 6;
```
If you declare the variable after it is used, but initialize it beforehand, it will return the value:
```javascript
num = 6;
console.log(num); // returns 6
var num;
```
JavaScript 仅提升声明，而不提升初始化。如果你先使用的变量，再声明并初始化它，变量的值将是 undefined。以下两个示例演示了相同的行为。
```javascript
// Example 1 - only y is hoisted
var x = 1;                 // 声明 + 初始化 x
console.log(x + " " + y);  // '1 undefined'
var y = 2;                 // 声明 + 初始化 y

// Example 2 - Hoists
var num1 = 3;                   // Declare and initialize num1
num2 = 4;                       // Initialize num2
console.log(num1 + " " + num2); //'3 4'
var num2;                       // Declare num2 for hoisting

// Example 3 - Hoists
a = 'Cran';              // Initialize a
b = 'berry';             // Initialize b
console.log(a + "" + b); // 'Cranberry'
var a, b;                // Declare both a & b for hoisting
```