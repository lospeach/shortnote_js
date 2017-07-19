

## [ Learning Es6: default parameter ]
**js**
```
function appDis(cost, discount) {
  discount = discount || .10;
  return cost - (cost * discount);
}
alert(appDis(100));
```
or
```
function appDis(cost, discount = .10) {
  return cost - (cost * discount);
}
alert(appDis(100));
```
or use this in case u have a multi funct.
```
function defaultAppDis(){
  return .10;
}
function appDis(cost, discount = defaultAppDis()) {
  return cost - (cost * discount);
}
```

> 90



## [ Learning Es6: Rest and Spread  ]

Rest <=> Spread

give me ANY number... or the REST of the number

**rest**
```
function sum(...numbers) {
  // now number is be equal to [1, 2, 3]
}

sum(1, 2, 3) // 6
```

```
function sum(...numbers) {
  return numbers.reduce(function(prev, current) {
    return prev + current;
  })
}

console.log(sum(1, 2, 3));

```

> get 6

**Spread**

```
function sum(x, y) {
    return x + y;
}

let nums = [1, 2];

console.log(sum(...nums));
```

> get 3

## [ Learning Es6: Template ]

ES6 make me enjoy creating a UI

```
let name = 'lospeach';

let template = `
<div class="info">
  <p>Hi, I am ${name}</p>
</div>
`;

console.log(template);
```

--Using backtick charactor not a comma or single quote--

## [ Learning Es6: Object ]

There are 3 things.
1. Obj. shorthand
2. Object Destructuring
3.

**1. normally We are using**
```
function getPerson() {

  let name = 'lospeach';
  let age = '25';

  return { name, age };

}

alert(getPerson().age);
```
> 25


**But in shorthand: Assign doing this**

we can assign many things to do in (return), so we also use shorthand defining a method.

```
...
// es5
    greeting: function () {
        return 'Say hi to ' + this.name;
    }
...
```

 a full code with short method syntex

```
//es6
function getPerson() {

  let name = 'lospeach';
  let age = '25';

  return {
    name,
    age,
    greeting() {
        return `
          Say hi to ${name}
        `
    }
   };
}

alert(getPerson().greeting());
```


Try calling a function and trigger a greeting method, you will get.

> Say hi to lospeach

**next 2. Object Destructuring**
we have obj. and then destructure a variable

for example in php
```
extract(['name', 'Jass']);
$name //Jass
```
destructure it and using it by call $name, than $name = Jass


```
let person = {

  name: 'Karen',
  age: 33

};

let{ name, age } = person;

alert(name);
```

> Karen

next

```
let data = {

  name: 'Karen',
  age: 33,
  result: ['foo', 'bar'],
  count: 43

};

let { result, count } = data;

console.log( result, count );
```

> ["foo", "bar"] 43

we can also use obj used as a function arguement

```
function getData({result, count}){
  console.log(result, count);
}

getData({
  name: 'Karen',
  age: 33,
  result: ['foo', 'bar'],
  count: 43
});
```

> ["foo", "bar"] 43 get a same thing

```
function greet({name, age}){
  console.log(`
    hello, ${name} and you are ${age}
  `);
}

greet({
  name: 'Karen Again',
  age: 33,
});
```

>  hello, Karen Again and you are 33
