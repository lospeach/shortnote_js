# Data Structure in JS
### Getting Started With DATA
**type of data**
- string 
```
var myVar = 'hello';
```
- number  
```

```
- boolean 
```
```
- object
```
```
- null
```
```
- undefined
```
```
- symbol (new in es6)
```
```

### Input and Output
**client side**
```
```
**server side**
```
```

### Control Structure
**Thare are 2 Control Structures.**
1.Iteration
  - while loop
  - do while
  - for loop
  - break
  - continue
2.Selection
  - if
  
### Function
  
```
```

### Class
The first method that all class should provide is **the constructor**. To creating and initializing an object with a class.
To see what method do, create a **show** method to log a result.
```
class doSum{

  constructor(myMoney, myExpense){
    this.tMoney = myMoney;
    this.tExpense = myExpense;
  }

  show() {
    console.log(`
      This is my total money =  ${this.tMoney - this.tExpense}.
    `);
  }

}

var myDoSum = new doSum(100, 65);

myDoSum.show();
```

We **never** call, invoke a class directly. 
To use a class, we use a name of class and pass the real/actual values.
```
var myDoSum = new doSum(100, 65);
```

and then use the instance name see below

```
myDoSum.show();
```

### Logic Gate
Read and or nand nor etc.


  
