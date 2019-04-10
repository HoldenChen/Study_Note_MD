### 1. `==` 和`===`
`===`和`!==`是严格比较符号，两个相比的对象类型必须一致。
- Two strings are strictly equal when they have the same sequence of characters, same length, 
and same characters in corresponding positions.
- Two numbers are strictly equal when they are numerically equal (have the same number value). 
NaN is not equal to anything, including NaN. Positive and negative zeros are equal to one another.
- Two Boolean operands are strictly equal if both are true or both are false.
- Two objects are strictly equal if they refer to the same Object.
- Null and Undefined types are == (but not ===). [I.e. (Null==Undefined) is true but (Null===Undefined) is false]

[参考链接](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)