# ES6：The Right Parts

### Arrow Function (箭头函数)

```javascript
() => 3
var foo = x => 3; foo.name; // 'foo'
(...x) => 3
(x,y) => 3
x => { return 3; }
x => ({ y: x })
foo = x => x > 5 ? x : 1    
```

### Let && Const

```javascript
// 块级作用域

```

### Default Value && Rest 参数

```javascript

var x = 1

function foo ( x= 2, f = function() { return x; }) {
  console.log( f() );
}

foo() // 2

```

```javascript

var x = 1

function foo ( x= 2, f = function() { return x; }) {
  var x = 5
  console.log( f() );
}

foo() // still 2

```

#### Rest && Spread

```javascript

function foo ( x, ...args ) {   // Rest参数 ...变量名
  console.log(args);
}

foo(2, 3)   // [2, 3]  打印其它参数,不包括X

```

```javascript
// 忽略第二个和第三个参数

function foo (x, y, z, ...rest) {
  return [x, ...rest]
}

function bar () {
  var a = [2, 4]
  var b = [6, 8, 10, 12]

  return foo(...a, ...b)
}

console.log(
  bar().join("") // 281012
);
```

### Destructuring and Default Value

```javascript
 var [
   a,
   b = 58,   // 如果a被赋值为undefined, a仍为默认值58
   c
 ] = [1, , 3] || []

```

```javascript
var a, b;

var x = [a, b] = [1, 2, 3, 4] // x = [1, 2, 3, 4]

```

#### Destructuring and Function Parameters

```javascript

function foo( {a , b = 10, c} = {}) {   // 防止未传参数
  console.log( a, b, c);
}

foo( {
  c: 3,
  a:1   // it works
})

```
