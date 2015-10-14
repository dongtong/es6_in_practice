# ECMAScript 6(2015) in Practice

* Tools
  
I use [es6fiddle.net](http://es6fiddle.net) online website to try es6 features.

* String Template

In ES5, we concat string by using following way:

    var part1 = "Hello ",
        greeting = part1 + "World";
    console.log(greeting); //Hello World
    
Now we could use ES6 string template as following:

    var part1 = "Hello",
        greeting = `${part1} world`;
    console.log(greeting);
    
    var greeting2 = `${part1}
       World
    `
String template will output as you want. It use ${} to introspect expression.

Examples:

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
    
Run: 

    Hello World
    Hello, ES6
          Welcome!
    3
    It's  0  I'm  awake
    
* Const

In ES5, we use var keyword and uppercase to define const variable. Now in ES6, we could use const keyword to define.

    const VALUE = 'Hello World';
    //VALUE = 'foobar'; //VALUE is read-only
    console.log(VALUE);

Once we define const variable, we could not modify its value, but we could modify its reference value as following:

    const person = {name: 'foobar'};
    person['age'] = 30;
    console.log(JSON.stringify(person)); // {"name":"foobar","age":30}
    
Const variable scope is block. In ES5 variable scope is functional, not block.

    if(true) {
      const name = 'foobar';
    }
    console.log('name: ', name); // name is not defined
    
    {
      const age = 30;
    }
    console.log('age: ', age); // age is not defined
