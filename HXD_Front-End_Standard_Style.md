# HTML Standard Style

### 语法

* **缩进使用soft tab（4个空格）；**
* **嵌套的节点应该缩进；**
* **属性名全小写，用中划线做分隔符；**
* **不要在自闭合标签结尾处使用斜线；**
* **不要忽略可选的关闭标签。**

### 属性顺序
* **HTML属性应该按照一定的顺序出现以保证易读性**
    * id
    * class
    * name
    * data-xxx
    * src, for, type, href
    * title, alt
    * disabled, checked, readonly

### 引号
* **属性的定义，统一使用双引号**
```html
<div class="content"> this is content </div>
```

### 嵌套

严格嵌套约束在所有的浏览器下都不被允许；而语义嵌套约束，浏览器大多会容错处理，生成的文档树可能相互不太一样。

* **严格嵌套约束**

    * inline-Level 元素，仅可以包含文本或其它 inline-Level 元素;
    * &lt;a &gt;里不可以嵌套交互式元素&lt;a &gt;、&lt;button &gt;、&lt;select &gt;等;
    * &lt;p &gt;里不可以嵌套块级元素&lt;div &gt;、&lt;h1 &gt;~&lt;h6 &gt;、&lt;p &gt;、&lt;ul &gt;&lt;ol &gt;&lt;li &gt;、&lt;dl &gt;&lt;dt &gt;&lt;dd &gt;、&lt;form &gt;等。

* **语义嵌套约束**

    * &lt;li &gt; 用于 &lt;ul &gt;或 &lt;ol &gt; 下；
    * &lt;dd &gt;, &lt;dt &gt;用于 &lt;dl &gt; 下；
    * &lt;thead &gt;, &lt;tbody &gt;, &lt;tfoot &gt;, &lt;tr &gt;, &lt;td &gt;用于 &lt;table &gt; 下；

### 布尔值属性
* **disabled、checked、selected 等属性不用设置值。**
 
 ```css
    /*  avoid  */
    <input type="text" disabled="disabled">

     /*  ok  */
    <input type="text" disabled>
    <input type="checkbox" value="1" checked>
 ```

# CSS Standard Style

### 缩进

* **使用四个空格缩进**。

  ```css
  .element {
        position: absolute;
        top: 10px;
        left: 10px;
   }
  ```
### 分号

* **每个属性声明末尾都要加分号**。

  ```css
  /* avoid */
  .element {
        position: absolute;
        top: 10px;
        left: 10px
   }

   /* ok */
  .element {
        position: absolute;
        top: 10px;
        left: 10px;
   }
  ```

### 空格

* 以下几种情况需要空格：

    * 属性值前<br>
    * 选择器'>', '+', '~'前后<br>
    * '{'前<br>
    * !important '!'前<br>
    * 属性值中的','后<br>
    * 注释'/*'后和'*/'前。

  ```css
    /* avoid */
    .element {
        color :red! important;
        background-color: rgba(0,0,0,.5);
    }

    /* ok */
    .element {
        color: red !important;
        background-color: rgba(0, 0, 0, .5);
    }

    /* avoid */
    .element ,
    .dialog{
        ...
    }

    /* ok */
    .element,
    .dialog {

    }

    /* avoid */
    .element>.dialog{
        ...
    }

    /* ok */
    .element > .dialog{
        ...
    }

    /* avoid */
    .element{
        ...
    }

    /* ok */
    .element {
        ...
    }
  ```
### 换行

* **每个属性独占一行，多个规则的分隔符'，'后**。

  ```css
    /* avoid */
    .element
    {color: red; background-color: black;}

    /* ok */
    .element {
        color: red;
        background-color: black;
    }

    /* avoid */
    .element, .dialog {
        ...
    }

    /* ok */
    .element,
    .dialog {
        ...
    }
  ```

### 引号

* **最外层统一使用双引号**
* **url的内容要用引号**
* **属性选择器中的属性值需要引号**

  ```css
    .element:after {
        content: "";
        background-image: url("logo.png");
    }

    li[data-type="single"] {
        ...
    }
  ```
### 命名

* **类名使用小写字母，以中划线分隔**
* **id采用驼峰式命名**
* **预处理器中的变量、函数、混合采用驼峰式命名**

  ```css
    /* class */
    .element-content {
        ...
    }

    /* id */
    #myDialog {
        ...
    }
  ```
### 属性声明顺序

* **常用属性书写顺序**

  ```js
    {
        [
            "display",     
            "visibility",
            "float",
            "clear",
            "overflow"
        ],
        [
            "flex-direction",
            "list-style",
            "flex"
        ],
        [
            "position",
            "top",
            "right",
            "bottom",
            "left",
            "z-index"
        ],
        [
            "margin",
            "padding",
            "border",
            "box-sizing",
            "border-radius",
            "border-image",
            "width",
            "min-width",
            "max-width",
            "height",
            "min-height",
            "line-height",
            "max-height",
            
        ],
        ['others']
    }

  ```

### 颜色

* **颜色使用16进制小写字母，并尽量简写**


  ```css
    /* avoid */
    .element {
        color: #ABCDEF;
        background-color: #001122;
    }

    /* ok */
    .element {
        color: #abcdef;
        background-color: #012;
    }
  ```

### 其它

* **不允许有空的规则**
* **元素选择器用小写字母**
* **去掉小数点前面的0**
* **去掉数字中不必要的小数点和末尾的0**
* **属性值'0'后面不要加单位**
* **无前缀的标准属性应该写在有前缀的属性后面**
* **不要在同个规则里出现重复的属性**
* **不要在一个文件里出现两个相同的规则**
* **尽量少用'*'选择器。**

  ```css
    /* avoid */
    .element {
        color: #ABCDEF;
        background-color: #001122;
    }

    /* ok */
    .element {
        color: #abcdef;
        background-color: #012;
    }
  ```


# JavaScript Standard Style


这是 JavaScript [standard](https://github.com/standard/standard) 代码规范的全文。

掌握本规范的最好方法是安装并在自己的代码中使用它。

### 缩进

* **使用四个空格**进行缩进 --diff。

  eslint: [`indent`](http://eslint.org/docs/rules/indent)

  ```js
  function hello (name) {
        console.log('hi', name)
  }
  ```
  
* **不要混合使用空格与制表符作为缩进**。

  eslint: [`no-mixed-spaces-and-tabs`](http://eslint.org/docs/rules/no-mixed-spaces-and-tabs)

* **除了缩进，不要使用多个空格**。

  eslint: [`no-multi-spaces`](http://eslint.org/docs/rules/no-multi-spaces)

  ```js
  const id =    1234    // ✗ avoid
  const id = 1234       // ✓ ok
  ```

### 分号

* **必须使用分号** --diff。

  ```js
  window.alert('hi');   // ✓ ok
  window.alert('hi')  // ✗ avoid

  var a = 1;           // ✓ ok
  var b = 2            // ✗ avoid
  ```

### 引号

* 除需要转义的情况外，**字符串统一使用单引号**。

  eslint: [`quotes`](http://eslint.org/docs/rules/quotes)

  ```js
  console.log('hello there')
  $("<div class='box'>")
  ```

* **不要定义未使用的变量**。

  eslint: [`no-unused-vars`](http://eslint.org/docs/rules/no-unused-vars)

  ```js
  function myFunction () {
    var result = something()   // ✗ avoid
  }
  ```

### 空格

* **关键字后面加空格**。

  eslint: [`keyword-spacing`](http://eslint.org/docs/rules/keyword-spacing)

  ```js
  if (condition) { ... }   // ✓ ok
  if(condition) { ... }    // ✗ avoid
  ```

* **函数声明时括号与函数名间不加空格** --diff。

  eslint: [`space-before-function-paren`](http://eslint.org/docs/rules/space-before-function-paren)

  ```js
  function name (arg) { ... }   // ✓ ok
  function name(arg) { ... }    // ✗ avoid

  run(function () { ... })      // ✓ ok
  run(function() { ... })       // ✗ avoid
  ```

* **赋值符号、字符串拼接、运算操作符 (Infix operators) 前后要留空格**。

  eslint: [`space-infix-ops`](http://eslint.org/docs/rules/space-infix-ops)

  ```js
  // ✓ ok
  var x = 2
  var message = 'hello, ' + name + '!'
  ```

  ```js
  // ✗ avoid
  var x=2
  var message = 'hello, '+name+'!'
  ```

* **逗号后面加空格**，前面不需要。

  eslint: [`comma-spacing`](http://eslint.org/docs/rules/comma-spacing)

  ```js
  // ✓ ok
  var list = [1, 2, 3, 4]
  function greet(name, options) { ... }
  ```

  ```js
  // ✗ avoid
  var list = [1,2,3,4]

  var arr = [ 1 , 2 , 3 , 4 ]

  var arr2 = [ 1, 2, 3, 4 ]

  function greet(name,options) { ... }
  ```

* **属性前面不要加空格**。

  eslint: [`no-whitespace-before-property`](http://eslint.org/docs/rules/no-whitespace-before-property)

  ```js
  user .name      // ✗ avoid
  user.name       // ✓ ok
  ```
* **展开运算符与它的表达式间不要留空白**。

  eslint: [`rest-spread-spacing`](http://eslint.org/docs/rules/rest-spread-spacing)

  ```js
  fn(... args)    // ✗ avoid
  fn(...args)     // ✓ ok
  ```

* **遇到分号时空格要后留前不留**。

  eslint: [`semi-spacing`](http://eslint.org/docs/rules/semi-spacing)

  ```js
  for (let i = 0 ;i < items.length ;i++) {...}    // ✗ avoid
  for (let i = 0; i < items.length; i++) {...}    // ✓ ok
  ```

* **代码块首尾留空格**。

  eslint: [`space-before-blocks`](http://eslint.org/docs/rules/space-before-blocks)

  ```js
  if (admin){...}     // ✗ avoid
  if (admin) {...}    // ✓ ok
  ```

* **圆括号间不留空格**。

  eslint: [`space-in-parens`](http://eslint.org/docs/rules/space-in-parens)

  ```js
  getName( name )     // ✗ avoid
  getName(name)       // ✓ ok
  ```

* **一元运算符后面跟一个空格**。

  eslint: [`space-unary-ops`](http://eslint.org/docs/rules/space-unary-ops)

  ```js
  typeof!admin        // ✗ avoid
  typeof !admin        // ✓ ok
  ```

* **注释首尾留空格**。

  eslint: [`spaced-comment`](http://eslint.org/docs/rules/spaced-comment)

  ```js
  //comment           // ✗ avoid
  // comment          // ✓ ok

  /*comment*/         // ✗ avoid
  /* comment */       // ✓ ok
  ```

* **模板字符串中变量前后不加空格**。

  eslint: [`template-curly-spacing`](http://eslint.org/docs/rules/template-curly-spacing)

  ```js
  const message = `Hello, ${ name }`    // ✗ avoid
  const message = `Hello, ${name}`      // ✓ ok
  ```

### 相等性判断

* 使用 `===` 替代 `==`，`!==` 替代 `!=`。<br>
  例外： `obj == null` 可以用来检查 `null || undefined`。

  eslint: [`eqeqeq`](http://eslint.org/docs/rules/eqeqeq)

  ```js
  if (name === 'John')   // ✓ ok
  if (name == 'John')    // ✗ avoid
  ```

  ```js
  if (name !== 'John')   // ✓ ok
  if (name != 'John')    // ✗ avoid
  ```
### 命名

* **对于变量和函数名统一使用驼峰命名法**。

  eslint: [`camelcase`](http://eslint.org/docs/rules/camelcase)

  ```js
    function my_function () { }    // ✗ avoid
    function myFunction () { }     // ✓ ok

    var my_var = 'hello'           // ✗ avoid
    var myVar = 'hello'            // ✓ ok
  ```

* **构造函数要以大写字母开头**。

  eslint: [`new-cap`](http://eslint.org/docs/rules/new-cap)

  ```js
  function animal () {}
  var dog = new animal()    // ✗ avoid

  function Animal () {}
  var dog = new Animal()    // ✓ ok
  ```

### 其它

* **始终使用let, const声明变量**，不依赖任何框架时除外。

  eslint: [`no-var`](http://eslint.org/docs/rules/no-var)

  ```js
  // ✓ avoid
  var silent = true;

  // ✗ ok
  let silent = true;
  ```

* **连续的变量声明，只使用一个关键字**。

  eslint: [`one-var`](http://eslint.org/docs/rules/one-var)

  ```js
  // ✓ avoid
  let silent = true;
  let verbose = true;

  // ✗ ok
  let silent = true,
      verbose = true;
  ```

* **else 关键字要与花括号**保持在同一行。

  eslint: [`brace-style`](http://eslint.org/docs/rules/brace-style)

  ```js
  // ✓ ok
  if (condition) {
    // ...
  } else {
    // ...
  }
  ```

  ```js
  // ✗ avoid
  if (condition)
  {
    // ...
  }
  else
  {
    // ...
  }
  ```

* **多行 if 语句的**的括号不能省。

  eslint: [`curly`](http://eslint.org/docs/rules/curly)

  ```js
  // ✓ ok
  if (options.quiet !== true) console.log('done')
  ```

  ```js
  // ✓ ok
  if (options.quiet !== true) {
    console.log('done')
  }
  ```

  ```js
  // ✗ avoid
  if (options.quiet !== true)
    console.log('done')
  ```
* **不允许有连续多行空行**。

  eslint: [`no-multiple-empty-lines`](http://eslint.org/docs/rules/no-multiple-empty-lines)

  ```js
  // ✓ ok
  var value = 'hello world'
  console.log(value)
  ```

  ```js
  // ✗ avoid
  var value = 'hello world'


  console.log(value)
  ```

* **开发模式下可以使用 `debugger`**，打包前要删除 --diff。

  eslint: [`no-debugger`](http://eslint.org/docs/rules/no-debugger)

  ```js
  function sum (a, b) {
    debugger      // ✗ avoid
    return a + b
  }
  ```
  
* **不要对变量使用 `delete` 操作**。

  eslint: [`no-delete-var`](http://eslint.org/docs/rules/no-delete-var)

  ```js
  var name
  delete name     // ✗ avoid
  ```

* **对象属性换行时注意统一代码风格**，每个属性单独一行。

  eslint: [`object-property-newline`](http://eslint.org/docs/rules/object-property-newline)

  ```js
  const user = {
    name: 'Jane Doe', age: 30,
    username: 'jdoe86'            // ✗ avoid
  }

  const user = {
    name: 'Jane Doe',
    age: 30,
    username: 'jdoe86'
  }                              // ✓ ok
  ```

* **请书写优雅的条件语句（avoid Yoda conditions）**。

  eslint: [`yoda`](http://eslint.org/docs/rules/yoda)

  ```js
  if (42 === age) { }    // ✗ avoid
  if (age === 42) { }    // ✓ ok
  ```

* **检查 `NaN` 的正确姿势是使用 `isNaN()`**。

  eslint: [`use-isnan`](http://eslint.org/docs/rules/use-isnan)

  ```js
  if (price === NaN) { }      // ✗ avoid
  if (isNaN(price)) { }       // ✓ ok
  ```

* **代码块中避免多余留白**。

  eslint: [`padded-blocks`](http://eslint.org/docs/rules/padded-blocks)

  ```js
  if (user) {
                              // ✗ avoid
    const name = getName()

  }

  if (user) {
    const name = getName()    // ✓ ok
  }
  ```
  
* **如果有更好的实现，尽量不要使用三元表达式**。

  eslint: [`no-unneeded-ternary`](http://eslint.org/docs/rules/no-unneeded-ternary)

  ```js
  let score = val ? val : 0     // ✗ avoid
  let score = val || 0          // ✓ ok
  ```
* **switch 一定要使用 break 来将条件分支正常中断**。

  eslint: [`no-fallthrough`](http://eslint.org/docs/rules/no-fallthrough)

  ```js
  switch (filter) {
    case 1:
      doSomething()    // ✗ avoid
    case 2:
      doSomethingElse()
  }

  switch (filter) {
    case 1:
      doSomething()
      break           // ✓ ok
    case 2:
      doSomethingElse()
  }

  switch (filter) {
    case 1:
      doSomething()
      // fallthrough  // ✓ ok
    case 2:
      doSomethingElse()
  }
  ```
* **函数调用时标识符与括号间不留间隔**。

  eslint: [`func-call-spacing`](http://eslint.org/docs/rules/func-call-spacing)

  ```js
  console.log ('hello') // ✗ avoid
  console.log('hello')  // ✓ ok
  ```

* **对于三元运算符** `?` 和 `:` 与他们所负责的代码处于同一行

  eslint: [`operator-linebreak`](http://eslint.org/docs/rules/operator-linebreak)

  ```js
  // ✓ ok
  var location = env.development ? 'localhost' : 'www.api.com'

  // ✓ ok
  var location = env.development
    ? 'localhost'
    : 'www.api.com'

  // ✗ avoid
  var location = env.development ?
    'localhost' :
    'www.api.com'
  ```


* **return 语句中的赋值必需有括号包裹**。

  eslint: [`no-return-assign`](http://eslint.org/docs/rules/no-return-assign)

  ```js
  function sum (a, b) {
    return result = a + b     // ✗ avoid
  }

  function sum (a, b) {
    return (result = a + b)   // ✓ ok
  }
  ```

# Vue.js Standard Style

* 参考官方[`风格指南`](https://cn.vuejs.org/v2/style-guide/)