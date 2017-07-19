##  Learning Es6: default parameter  

**es6**

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
