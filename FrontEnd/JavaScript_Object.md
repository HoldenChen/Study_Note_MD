#数组 
通过从0开始的下标访问
```
const singleArray = ['single'];
const mixArray = [1,'hello',true,singleArray];
console.log(mixArray[0]);
```
##数组方法
### `forEach()`
```
[1, 5, 2, 4, 6, 3].forEach(function logIfOdd(n) {
  if (n % 2 !== 0) {
    console.log(n);
  }
});

// 1
// 5
// 3
```

### `map()`
```
const musicData = [
    ...
];

const albumSalesStrings = musicData.map(function(music){
    return music.name +' by '+music.artist +' sold '+music.sales +' copies';
});

console.log(albumSalesStrings);
```

### `filter()`
```
const musicData = [
    { artist: 'Adele', name: '25', sales: 1731000 },
    ...
];

const results = musicData.filter(function(music){
    if(music.name.length >= 10 && music.name.length <= 25){
        return music;
    }
});

console.log(results);
```
### 数组解构
```
const point = [0,1,2];
const [x,y,z] = point;
console.log(x,y,z);
```
  
      
    
#对象
对象是有关联的键值对的集合。  
对象的键为字符串，默认可以不用引号 `''`,当以保留字作为键时需要使用  
引号。
---
###对象的定义
```
 const car = {
   color : 'read',
   year : 2008,
   isPreOwned :true
 };
```
###访问对象属性
```
const bicycle = {
    color : 'blue',
    type : 'mountain bike',
    wheels:{
        diameter : 18,
        width:8
    }
};

//点表示法
bicycle.color; //'blue'
bicycle.wheels.diameter;
//方括号表示法
bicycle['color']; //'blue'
bicycle['wheels']['diameter'];
```

*点表示法的局限*  
- 键为数字时，无法正常访问。
- 将变量作为属性名称是无法正常访问。

###调用对象方法
```
const developer = {
    name : 'holden',
    sayHello : function(){
        console.log('hello');
    }
}

developer.sayHello();
developer['sayHello']();
```
### 对象解构
```
const gemstone = {
  type : 'quartz',
  color : 'rose',
  karat : 21.29
};

const {type,color,karat} = gemstone;
console.log(type, color, karat);
```

##this 关键字
根据函数被调用的方式 `this` 会被设置为不同的值。

1. 使用new关键字调用 `构造函数` 会将`this`设置为一个新创建的对象。
2. 调用属于一个对象的函数，会将`this`设置为该对象本身。
3. 单独调用一个函数(常规调用)，会将`this`设置为 `window`
4. 调用函数的方式可以让我们自己设置`this`.
   > `apply()`  
   
   > `call()`  
   
   >  `bind()`
   

###箭头函数内的`this`
   基于函数周围的上下文
      
##对象方法  `Object.keys()` `Object.values()`

```
const dictionary = {
  car: 'automobile',
  apple: 'healthy snack',
  cat: 'cute furry animal',
  dog: 'best friend'
};

Object.keys(dictionary);
Object.values(dictionary);
```
`Object.values` 返回的数组元素是字符串，且与 `for...in` 返回的顺序一致。

#函数
##一级函数      
JavaScript 中的函数可以像对象，数组，字符串等一样处理：

- 存储于变量中
- 从函数中返回
- 作为参数传给另外一个函数

**函数和对象的重要区别是，函数可以通过`()`来执行，常规对象则不行！**

##回调函数
作为参数传递给另一个函数的函数  称作 回调函数。

##高阶函数
接受其它函数作为参数的函数，称作 高阶函数。

##作用域
- `let`
- `const`

最里面的函数拥有最大的访问范围。   

##箭头函数
 > 单个参数  可以省略 `()`  
   - `const greet = name => 'Hello ${name}!`
   
 > 0个或者多个参数 必须带 `()`
 ```
  const orderConstIceCream = (flavor,cone) => console.log(
  `Here's your ${flavor} icecream in a ${cone} cone.`);
 ```
  
    `const sayHi = () => console.log("Hello there");`
##简写主体法
- 函数主体周围没有花括号。    
- 自动返回表达式。
```
const upperizedNames = ['Farrin', 'Kagure', 'Asser'].map(
  name => name.toUpperCase()
);
```

##常规主体语法
- 函数主体在花括号内。
- 需要使用`return` 返回内容。

```
const upperizedNames = ['Farrin', 'Kagure', 'Asser'].map( name => {
  name = name.toUpperCase();
  return `${name} has ${name.length} characters in their name`;
});
```    

##默认函数参数



#JavaScript类

