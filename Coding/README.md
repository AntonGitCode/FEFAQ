## приведение типов
  
```javascript
const obj = {
  valueOf: () => 42,
  toString: () => 27
};
console.log(obj + '');
```
  
## scopes

```javascript
function foo() {
    console.log(a);  // ???
}
  
function bar() {
    var a = 3;
    foo();
}

var a = 5;
bar();
```

```javascript
function bar() {
  var a = 3;

  function foo() {
    console.log(a);
  }
  
  foo();
}

var a = 5;
bar();
```
  
  
##  дубликат массива  

```javascript
function duplicate(array) {
  for (var i = 0; i < array.length; i++) {
    array.push(array[i]);
  }
  return array;
}

const arr = [1, 2, 3];
const newArr = duplicate(arr);
console.log(newArr); // ?
```
  
## количество повторений  
  
```javascript  
const input = [1, 2, 2, 2, 2, 3, 1, 1, 3, 4, 4];
const count = {};

// Подсчет количества повторений
for (let i = 0; i < input.length; i++) {
  const element = input[i];
  count[element] = (count[element] || 0) + 1;
}

// Создание строки output
let output = '';
for (const key in count) {
  if (count.hasOwnProperty(key)) {
    output += `${key}:${count[key]}, `;
  }
}

// Удаление последней запятой и пробела из строки output
output = output.slice(0, -2)

console.log(output);
```

## cb

```javascript
var length = 4;
function cb(){
  console.log(this.length);
}

const obj = {
  length: 5,
  method(cb) {
    cb();
  }
} 

obj.method(cb);
```

## event-loop  
  
```javascript
console.log(1);
setTimeout(() => console.log(2));
Promise.resolve().then(() => console.log(3));
Promise.resolve().then(() => setTimeout(() => console.log(4)));
Promise.resolve().then(() => console.log(5));
setTimeout(() => console.log(6));
console.log(7);
```
  
  

## приведение типов
  
```
true + false
12 / "6"
"number" + 15 + 3
15 + 3 + "number"
[1] > null
"foo" + + "bar"
'true' == true
false == 'false'
null == ''
!!"false" == !!"true"
['x'] == 'x'
['x'] == ['x']
[] + null + 1
0 || "0" && {}
[1,2,3] == [1,2,3]
{}+[]+{}+[1]
!+[]+[]+![]
new Date(0) - 0
new Date(0) + 0
[1/Infinity] <= null
```

## еще на приведение типов

```javascript
0 == false   // true
0 === false  // false
1 == "1"    // true 
1 === "1"    // false
null == undefined // true

null === undefined // false
'0' == false // false //true
'0' === false  //false
[]==[] or []===[] //false
{}=={} or {}==={}
```

## задачка  
```javascript
for (const i in [1,2,3]) {
  try {
    console.log(i);
    break;
  }
  finally {
    continue;
  }
}
```
  
## task  

```
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
console.log(foo.x);
console.log(bar);
```

## THIS

```javascript
let user = {
  sayHi: function() { alert(this);}
};

(user.sayBye = user.sayHi)();
```

```javascript
let user = {
  method() {console.log(this)}
};
let fun = obj.method;
fun();
```
  
## this
```javascript
function foo(num) {
  console.log('foo', num);
  window.count++;
}

foo.count = 5;
globalThis.count = 4;

var i;
for (i=0; i<10; i++) {
  if (i>5) foo(i);
}

console.log(window.count);
```

  
## связывание  

```javascript
function a() {
 alert(this);
}
a();
a.call(null);
```

```javascript
let user = {
  sayHi: function() { console.log(this); }
};

(user.sayBye = user.sayHi).bind(user)();
```

## связывание еще  

```javascript
'use strict'
var a = {
  firstName: 'Bill',
  lastName: 'Ivan',
  sayName: function() {
    console.log(this.firstName);
  },
  sayLastName: () => {
    console.log(this.lastName);
  }
}

 a.sayName();
 // var b = a.sayName;
 // b();
 
a.sayName.bind({firstName:'Mark'})();
a.sayName();

var c = a.sayName.bind({firstName:'C-name'});
c();

a.sayName.call({firstName:'Call'});

var d = a.sayName;
d.bind({firstName:'Repeat this rule'})();

a.sayName.bind({firstName: 'first node'}).bind({firstName: 'second node'})();

a.sayLastName.bind({lastName:'Lasttt'})();
```
 
## prototype this.  
  
```  
String.prototype.log = function() {
  console.log(this.toString());
};

const test = {
  toString: () => 'this test'
}

str.log call(test);
```  
## промис-хелл  
  
```
const firstPromise = new Promise((resolve, reject) => {
  setTimeout(resolve, 500, 'odin');
});

const secondPromise = new Promise((resolve, reject) => {
  setTimeout(resolve, 100, 'dva');  
})

Promise.any([firstPromise, secondPromise]).then(res=>console.log('res ', res)).catch(err=>console.log('err ', err));
Promise.allSettled([firstPromise, secondPromise]).then(res=>console.log('res ', res)).catch(err=>console.log('err ', err));
```
  
## промис хелл
  
```javascript
function test() {
  return new Promise((res) => {
   console.log('5'); 
   setTimeout(() => res(6), 1000);
  })
}

console.log('1')

test()
  .then(v => {
    throw new Error(v);
  })
  .then((v) => {
    throw new Error(v*2);
  })
  .finally(() => console.log('2'))
  .catch((v) => console.log('vv ', v.message));

Promise.resolve('3').finally(() => { 
 throw new Error('4')
})
 .then((v) => console.log('v2 ', v))
 .catch((v) => console.log('v3 ', v.message));

console.log('7');

//// 1 5 7  4 2 6
```  
  
  
## сравнение двух объектов  
  
```javascript
function A(){ return 'stroka'; }
function B(){ return 'stroka'; }
let a = new A;
let b = new B;
console.log(a === b);
```
```javascript
function A(){ return arr; }
function B(){ return arr; }
let arr = [];
let a = new A;
let b = new B;
console.log(a === b);
```
## написать функцию проверяет строку на палиндром
```
function isPalindrom(str) {
    const strPure = str.toLowerCase().replace(/[^a-z0-9]/gi,""); 
    let left =0;
    let right = strPure.length-1;
    while (left<right) {
      if (strPure[left]!==strPure[right]) return false;
      left++;
      right--;  
    }
    return true;
}
```
## event loop

```javascript
console.log(1);

setTimeout(()=> {
  console.log(2);
})

requestAnimationFrame(() => {
  console.log(6);
})


new Promise((res)=> {
  console.log(3);
  res();
}).then(()=>{
  console.log(5);
  queueMicrotask(()=> {
    console.log(7);
  })
}) 

console.log(4);
```
  
## промисс  
  
```
 Promise.resolve()
     .then(() => console.log(1))  // "Первый"
     .then(() => console.log(2));  // "Третий"

 Promise.resolve()
     .then(() => console.log(11)) // "Второй"
     .then(() => console.log(12)); // "Четвертый"
```  
  
## promise hell

```javascript
const a = setTimeout(() => console.log(2), 2000);
const d = setTimeout(() => console.log(6), 1000);

const c = new Promise( (resolve) => { 
   setTimeout(() => resolve(), 1000);
   console.log(4);
});

c.then(() => console.log(1));

const b = setTimeout(() => console.log(5), 1000);

console.log(3);
```
// 4 3 6 1 5 2

```javascript
setTimeout(() => console.log(3), 2000);
console.log(4);

new Promise((res, rej) => {
    setTimeout(() => res());
})
    .then(() => console.log(1))
    .catch(() => console.log(2));

queueMicrotask(() => {
    console.log(5);
    queueMicrotask(() => {
        requestAnimationFrame(() => {
            console.log(8);
        });
        queueMicrotask(() => {
            console.log(7);
        });
    });
});

requestAnimationFrame(() => {
    console.log('raf3');
    requestAnimationFrame(() => {
        console.log(6);
    });
});

console.log(9);     
```

  // 4 9 5 7 raf3 8 1 6 3  

# this в функциях и в () => {} 

```javascript
'use strict'
const user = {
    name: 'Bob',
    funcFunc() {
        return function () {
            console.log(this);
        }
    },
    funcArrow() {
        return () => {
            console.log(this);
        }
    },
    arrowFunc: () => {
        return function () {
            console.log(this);
        }
    },
    arrowArrow: () => {
        return () => {
            console.log(this);
        }
    },
};

user.funcFunc()(); // undef
// undefined
user.funcArrow()(); // user
// user
user.arrowFunc()(); // undef
// undefined
user.arrowArrow()(); // undef
// undefined
```

## еще про this

```javascript
'use strict'
const user = {
  name: 'user',
  funcFunc() {
     return function() {
       console.log(this.name);
     }
   },
  funcArrow() {
    return () => { 
      console.log(this.name);
    }
  },
  arrowFunc: () => {
    return function() {
      console.log(this.name);
    }
  },
  arrowArrow: () => {
    return () => {
      console.log(this.name);
    }
  },
};

const user2 = {
  name: 'user2', 
  funcFunc: user.funcFunc(), 
  funcArrow: user.funcArrow(), 
  arrowFunc: user.arrowFunc(), 
  arrowArrow: user.arrowArrow(),
}

// user2.funcFunc(); //  Jim
// user2.funcArrow(); // Bob
// user2.arrowFunc(); // Jim
// user2.arrowArrow();  // undef
```
  

## на прототипы  

```javascript
var animal = { jumps: null };
var rabbit = { jumps: true };

rabbit.__proto__ = animal;

console.log( rabbit.jumps ); // true


delete rabbit.jumps;
console.log( rabbit.jumps ); // null


delete animal.jumps;
console.log( rabbit.jumps); // undefined 
```

## на мемоизацию

```javascript  
const add = () => {
  const cache = {};
  return num => {
  if (num in cache) {
    return `From cache: ${cache[num]}` 
  } else {
    const result = num + 10;
    cache[num] = result;
    return `Calculated: ${result}`;
}
};
};

const addFunction = add(1100); 
// console.log(addFunction);
// console.log(addFunction(10)); 
// console.log(addFunction(1));
// console.log(addFunction());
// console.log(addFunction(50));
```

<hr></hr>
<img src="https://github.com/AntonGitCode/FEFAQ/assets/117078390/dce617bf-b6c7-42a2-b521-ce5322f3651f" width=700>
<hr></hr>
<img src="https://github.com/AntonGitCode/FEFAQ/assets/117078390/c7e315b4-38ba-4017-b2ae-a89ade2e63a9" width=350>
 <hr></hr> 
  


## Примеры кода на JavaScript

Вопрос: Какое значение будет у foo?
~~~~javascript
var foo = 10 + '20';
~~~~
Ответ: '1020'. Приведение типов преобразует 10 в строку и сложит 2 строки.


Вопрос: Что будет выведено в консоль?
~~~~javascript
console.log(0.1 + 0.2 == 0.3);
~~~~
Ответ: false. Из-за плавающей точки результатом вычисления будет 0.30000000000000004. Чтобы справится с этой проблемой нужно округлять числа до десятков.


Вопрос: Как сделать так, чтобы приведенный ниже код работал?
~~~~javascript
add(2, 5); // 7
add(2)(5); // 7
~~~~
Ответ:
~~~~javascript
function add(a, b) {
  return a && b ? a + b : function (c) { return a + c; };
}
~~~~


Вопрос: Какое значение будет возращено?
~~~~javascript
"i'm a lasagna hog".split("").reverse().join("");
~~~~
Ответ: `'goh angasal a m\'i'`


Вопрос: Какое значение будет у window.foo?
~~~~javascript
( window.foo || ( window.foo = "bar" ) );
~~~~
Ответ: 'bar'


Вопрос: Какой будет результат приведенного ниже кода?
~~~~javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
~~~~
Ответ:
1. `Hello World` из функции.
2. `ReferenceError: bar is not defined` т.к переменная `bar` бар определена в области видимости функции и не видна за ее пределами. 


Вопрос: Чему равно foo.length?
~~~~javascript
var foo = [];
foo.push(1);
foo.push(2);
~~~~
Ответ: 2;


Вопрос: Чему равно foo.x?
~~~~javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
~~~~
Ответ: `undefined`. 
`foo.x = foo = {n: 2}` то же, что и `foo.x = (foo = {n: 2})`. `foo` на которую ссылается `foo.x` "устанавливается" перед тем, как `foo` изменится. `foo.x` ссылается на старое значение `foo`. Это значит, что в старом `foo` появится новое свойство `x` равное `{n: 2}`. А в новое `foo` запишется `{n: 2}`. Значение старого `foo` находится в `bar`.
~~~~javascript
{
  n: 1,
  x: {
    n: 2
  }
}
~~~~
Так как при дальнейшем выводе `foo.x` наше `foo` ссылается на его новое значение, в котором отстутствует `x`, то `foo.x` будет неопределено.


Вопрос: Что будет выведено в консоль?
~~~~javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
Promise.resolve().then(function() {
  console.log('three');
})
console.log('four');
~~~~
Ответ: 'one', 'four', 'three', 'two'. `setTimeout` часть основной очереди (main task queue), тогда как `Promise` в miscro task queue, которая выполняется перед основной. Поэтому сначала выведентся 'three', а потом 'two'.
