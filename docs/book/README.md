## 《你不知道的Javascript（中卷）》
## 简介
   你不知道的Javascript（中卷）主要有两部分组成：类型和语法、异步和性能
### 类型
  >变量没有类型，但它们持有的值有类型。类型定义了值的行为特征
### undefined 和 undeclared
   Javascript将undefined和undeclared混为一谈，实际上它们是两码事。

  - undefined是值的一种，是已在作用域中声明但还没有赋值的变量；
  - undeclared则表示变量还没有被声明过；
  
  但 令人抓狂的一点在于 typeof 的处理方式：

  ```js
  var a 
  console.log(a) // undefined
  console.log(b) // ReferenceError: b is not defined
  typeof a      // 'undefined'
  typeof b     // 'undefined'
  ```
  typeof 对undefined和undeclared变量都返回'undefined'；<br/>
  这是typeof的防范机制，如果一个变量未声明，使用typeof不会报语法错误，而是会返回'undefined';
  可以用来判断一个变量是否存在