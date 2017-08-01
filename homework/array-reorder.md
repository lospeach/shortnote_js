## HW1
var oldArray = [3,1,2,5];
need to add new 6 
and reorder it for min to max

**let' start**

```
var oldArray = [4, 5, 1, 3]; //(4) [4, 5, 1, 3]
console.log(oldArray);
oldArray.push(7);
var newArray = oldArray;
console.log(newArray.sort()); //(5) [1, 3, 4, 5, 7]

```

what about reorder it for max to min

```
console.log(newArray.sort().reverse()); //(5) [7, 5, 4, 3, 1]
```

## HW2
find a number which less than 16
var item2 = [12, 5, 8, 129, 67];

**let' start**
same concept, need to compare between number in array and 16 

```
for (var i = 0; i <= 129; i++) {
  var a = item2[i] <= 16;
  var b = item2[i] == i;
  if (a != b) {
    console.log(item2[i]); // 12 5 8
  }
}

```

or use Array.prototype.filter()
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter

```
function isBigEnough(value) {
  return value <= 16;
}

var filtered = item2.filter(isBigEnough);

console.log(filtered); //(3) [12, 5, 8]
```

Filtering invalid entries from JSON

