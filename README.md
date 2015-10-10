# ECMAScript 6(2015) in Practice

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
