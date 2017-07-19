# shortnote_js

## A Basic Modifying Classes

```
function addClass(selector, myClass) {
  // get all elements that match our selector
  let elements = document.querySelectorAll(selector);

  // add class to all chosen elements
  for (var i=0; i<elements.length; i++) {
    elements[i].classList.add(myClass);
  }
}
```

** usage examples: **
```
addClass('.class-selector', 'example-class');
addClass('#id-selector', 'example-class');
```


```
function removeClass(selector, myClass) {

  // get all elements that match our selector
  let elements = document.querySelectorAll(selector);

  // remove class from all chosen elements
  for (var i=0; i<elements.length; i++) {
    elements[i].classList.remove(myClass);
  }
}
```

** usage examples: **
```
removeClass('.class-selector', 'example-class');
removeClass('#id-selector', 'example-class');
```
