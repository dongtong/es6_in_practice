# ECMAScript 6(2015) in Practice

## 1. 在线开发工具
  
   使用 [es6fiddle.net](http://es6fiddle.net)

## String 模版

在ES5中, 我们经常通过以下方式连接字符串:

    var part1 = "Hello ",
        greeting = part1 + "World";
    console.log(greeting); //Hello World
    
ES6中可以使用字符串模版连接:

    var part1 = "Hello",
        greeting = `${part1} world`;
        
    console.log(greeting);
    
    var greeting2 = `${part1}
       World
    `
字符串模版会按照你预期的结果输出，通过${}自省执行表达式。

示例:

    var part1 = "Hello",
    greeting = `${part1} World`;
    console.log(greeting);

    var part2 = "Hello",
        greeting2 = `${part2}, ES6
      Welcome!`;

    console.log(greeting2);

    var a = 1,
        b = 2,
        c = `${a + b}`;

    console.log(c);

    function tag(strings, ...values) {
        if(values[0] < 20) {
            values[1] = "awake";
        }
        return `${strings[0]} ${values[0]} ${strings[1]} ${values[1]}`;
    }
    
运行结果: 

    Hello World
    Hello, ES6
          Welcome!
    3
    It's  0  I'm  awake
    
## 常量

在ES5中通过定义大写字母的变量作为常量， ES6中通过const定义常量.

    const VALUE = 'Hello World';
    //VALUE = 'foobar'; //VALUE is read-only
    console.log(VALUE);

一旦定义常量，将无法改变它的值，但是如果常量定义成字面量对象，可以修改它引用的值:

    const person = {name: 'foobar'};
    person['age'] = 30;
    console.log(JSON.stringify(person)); // {"name":"foobar","age":30}
    
常量作用域是块级作用域。在ES5中作用域是函数级别的。

    if(true) {
      const name = 'foobar';
    }
    console.log('name: ', name); // name is not defined
    
    {
      const age = 30;
    }
    console.log('age: ', age); // age is not defined
    
## 默认参数

ES5中无法給函数参数设定默认值，但是在ES6中可以设置:

    function greet(name="foobar", word='Hello, World') {
      console.log(name);
      console.log(word);
    }

    greet(); //foobar Hello, World
    greet("chachacha"); // chachacha Hello, World
    greet(..."Hello, ES6"); // H, e
    
可以传递一个函数作为默认值.

    function greet(speak = ()=> console.log("Hello, World")){
        speak();
    }
    greet(); // Hello, World

##Spread/Rest操作符

Spread(扩展操作符),将可迭代对象(数组居多)中每一个元素扩散(spread)开,赋值給不同的值。

示例:

    function add(a, b) {
        return a + b;
    }

    let nums = [5, 4];

    console.log(add(...nums));

示例:

    let arr1 = [2,3];
    let arr2 = [1, ...arr1, 4];
    console.log(arr2);
