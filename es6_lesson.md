# Learning Es6

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



## [ Learning Es6: Class ]
**es5**
```
// 1. create a constructure
function User(username, email){
  //assign attribute to it
  this.username = username;
  this.email = email;
}

//2. create prototype obj: for any method u wanna share attached to prototype
User.prototype.changeEmail = function(newEmail) {
  //method that want to do (share method)
  this.email = newEmail;
};

//3. assign it (old one)
var user = new User('LospeachWay', 'info@mail.com')

// 4. use it
user.changeEmail('new_info@mail.com')

//5.  see a result
console.dir(user);
```

but

**es6**
```
// 1. create class
class User {

// 3. declare username, email we will do it in constructure
  constructure(username, email) {
    this.username = username;
    this.email = email;
  }

// 2. create method
  changeEmail(newEmail) {
    //assign what it will do
    this.email = newEmail;
  }
}

 //4.  assign it (old one)
let user = new User('LospeachWay', 'info@mail.com');

// 5. use it
user.changeEmail('new_infoagain@mail.com');

//6.  see a result
console.dir(user);
```

or

```
// 1. create class
class User {
  get somthing() {
    return 'sunday';
  }
}
//2.  assign it (old one)
let user = new User();

//3.  see a result
console.log(user.somthing); //sunday
```




## [ Learning Es6: Promise ]
 Meaning: promise (I promise that perform the action or I will do blablabla for u I promise) holding a oporation (method, event) that it not taking place
 the will per form an action.

**js**

This is a promise syntex...

```
promise.then(function(data) {
  /*i will do blablabla for u when it's time.*/
});
promise.catch(function(err) {
  // when st went wrong u promise, that u will sent a err msg.
});
```

as

```
promise.then(function(data) {
  /*i will do blablabla for u when it's time.*/
}).catch(function(err) {
  // when st went wrong u promise, that u will sent a err msg.
});
```

same as

```
promise.then(function(data) {
  /*i will do blablabla for u when it's time.*/
}) , function(err) {
  // when st went wrong u promise, that u will sent a err msg.
});
```

a real used of promise

```
var timer = new Promise(function (resolve, reject) {

  console.log('Init Promise');

  setTimeout(function () {

    console.log('Time Done!!!!');

  }, 3000);

});

timer.then( function () {

  console.log('Timer has concluded!!!');

});
```
>Init Promise
wait 3 sec then
> Time Done!!!!

u need to call both resolve and reject function
we need to assign when do u want to resolve() or reject()

```
var timer = new Promise(function (resolve, reject) {

  console.log('Init Promise');

  setTimeout(function () {

    console.log('Time Done!!!!');

    resolve();

  }, 3000);

});


timer.then( function () {

  console.log('Timer has concluded!!!');

});

```

>Init Promise
wait 3 sec then
> Time Done!!!!
Timer has concluded!!!

let's turn a timer to a function

```
var timer = function(length) {

  return new Promise(function (resolve, reject) {

    console.log('Init Promise');

    setTimeout(function () {

      console.log('Time Done!!!!');

      resolve();

    }, length);

  });

};

timer(5000).then(() => alert('Yo, It is cool.'));
```

## [ Learning Es6: Useful String Additions ]

instead of using this
```
let title = 'Red Silly';

if (title.indexOf('R') == 0 ) {
  console.log('There is R');
}
// !
if (title.indexOf('B') == -1 ) {
  console.log('There is no B');
}
```

use this includes() instead
```
let title = 'Red Silly';

if (title.includes('R')) {
  console.log('There is R');
}
```

> more:
'string'.includes()
'string'.startsWith(),
'string'.endsWith(),
find with position/index find i at index 5th(start at index 0)
'string'.startsWith('i', 5),

more, try
```
let str = 'hahahaha';
console.log(str + 'lol'.repeat(11));
```

>hahahahalollollollollollollollollollollol

and

```
let aTitle = 'The title is here.';
console.log('='.repeat(5) + aTitle + '='.repeat(5));
```

>=====The title is here.=====

or es6 way

```
let aTitle = 'The title is here.';
console.log(`
   ${'='.repeat(5)} ${aTitle} ${'='.repeat(5)}
`);
```

>   ===== The title is here. =====




## [ Learning Es6: Module ]
**html**
```

```
**css**
```

```
**VUE**
```

```
