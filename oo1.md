## Arrays in JavaScript

### create

```
var test = function(array) {
  console.log('length:'+ array.length);
  array.forEach(function(element, index, array) {
    console.log(index + ':' + element);
  });
};
```
### Length
```
var arr = ['a','b','c','d','e','f',,,];
test(arr);
```
-- length:8, 0:a, 1:b, 2:c, 3:d, 4:e, 5:f --

array 6: and 7: are blank

### Remove

There are three methods pop, shift and splice that can remove entries from the array.

** pop() removes the last element from an array **
```
var arr = ['a','b','c','d','e','f'];
var el = arr.pop();
test(arr); // length:5, 0:a, 1:b, 2:c, 3:d, 4:e
console.log(el); // f
```

** shift() removes the first element from an array **
```
var arr = ['a','b','c','d','e','f'];
var el = arr.shift();
test(arr); // length:5, 0:b, 1:c, 2:d, 3:e, 4:f
console.log(el); // a
```

** splice() can remove existing elements **
```
var arr1 = ['a','b','c','d','e','f'];
var arr2 = arr1.splice(0,2); // remove 2 elements starting at index 0
test(arr1); // length:4, 0:c, 1:d, 2:e, 3:f
test(arr2); // length:2, 0:a, 1:b


var arr1 = ['a','b','c','d','e','f',,,'i'];
var arr2 = arr1.splice(6,2); // remove 2 elements starting at index 6
test(arr1); // length:7, 0:a, 1:b, 2:c, 3:d, 4:e, 5:f, 6:i
test(arr2); // length:2
```

### Add
```
var arr = ['a','b','c','d','e','f',,,'i'];
arr[11] = 'l';
test(arr);
```
-- length:12, 0:a, 1:b, 2:c, 3:d, 5:f, 8:i, 11:l --

-- push() adds one or more elements to the end of an array --
```
var arr = ['a','b','c','d','e','f',,,,];
arr.push('j');
test(arr);
```
-- length:10, 0:a, 1:b, 2:c, 3:d, 5:f, 9:j  --

-- unshift() adds one or more elements to the beginning of an array  --
```
var arr = ['a','b','c','d','e','f',,,,];
arr.unshift('x');
test(arr);
```
-- length:10, 0:x, 1:a, 2:b, 3:c, 4:d, 5:e, 6:f  --
```
arr1 = ['a','b','c','d','e','f',,,'i'];
arr2 = arr1.splice(6,0,'g','h'); // removes 0 elements from index 6, and inserts 'g', 'h'
test(arr1); // length:11, 0:a, 1:b, 2:c, 3:d, 5:f, 6:g, 7:h, 10:i
test(arr2); // length:0
```

and the last one

### replace
```
var arr1 = ['a','b','c','d','e','f',,,'i'];
var arr2 = arr1.splice(6,2,'g','h');
test(arr1); // length:9, 0:a, 1:b, 2:c, 3:d, 4:e, 5:f, 6:g, 7:h, 8:i
test(arr2); // length:2
```




