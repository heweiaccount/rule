## 一、常用格式化规范

#### .prettierrc 文件常见配置

```html
1.vscode可以在项目根目录下配置.prettierrc文件，webstorm小伙伴自行根据配置规则适配一下
2.格式化风格不强求所有项目统一，但多人负责同一项目时，最好以初始化项目者的风格为准
```

```json5
{
  // tab缩进大小,默认为2
  tabWidth: 2,

  // 使用tab缩进，默认false
  useTabs: true,

  // 使用分号, 默认true
  semi: true,

  // 使用单引号, 默认false(在jsx中配置无效, 默认都是双引号)
  singleQuote: true,

  // 行尾逗号,默认none,可选 none|es5|all
  // es5 包括es5中的数组、对象
  // all 包括函数对象等所有可选
  TrailingCooma: "es5",

  // 对象中的空格 默认true
  // true: { foo: bar }
  // false: {foo: bar}
  bracketSpacing: true,

  // JSX标签闭合位置 默认false
  // false: <div
  //          className=""
  //          style={{}}
  //       >
  // true: <div
  //          className=""
  //          style={{}} >
  jsxBracketSameLine: false,

  // 箭头函数参数括号 默认avoid 可选 avoid| always
  // avoid 能省略括号的时候就省略 例如x => x
  // always 总是有括号
  arrowParens: "avoid",
}
```

---

## 二、常用代码规范

### 文件命名

普通 JS/TS 文件以小写字母命名，多个单词以下划线连接，例如 `util.js`、`util_helper.js`

组件文件命名遵循 Pascal 命名法，例如 `ReservationCard.jsx`、`ReservationCard.vue`

## JavaScript 书写规范

### 基本书写

#### 使用两个空格进行缩进

> 不要混合使用空格与制表符作为缩进

```javascript
function hello(name) {
  console.log("hi", name); // ✓ 正确
  console.log("hello", name); // ✗ 错误
}
```

#### 除了缩进，不要使用多个空格

```javascript
const id = 1234; // ✗ 错误
const id = 1234; // ✓ 正确
```

#### 不要在句末使用分号

```javascript
const a = "a"; // ✓ 正确
const a = "a"; // ✗ 错误
```

#### 字符串统一使用单引号

```javascript
console.log("hello there");
// 如果遇到需要转义的情况，请按如下三种写法书写
const x = 'hello "world"';
const y = "hello 'world'";
const z = `hello 'world'`;
```

#### 代码块中避免多余留白

```javascript
if (user) {
  // ✗ 错误
  const name = getName();
}

if (user) {
  const name = getName(); // ✓ 正确
}
```

#### 关键字后面加空格

```javascript
if (condition) { ... }   // ✓ 正确
if(condition) { ... }    // ✗ 错误
```

#### 函数声明时括号与函数名间加空格

```javascript
function name (arg) { ... }   // ✓ 正确
function name(arg) { ... }    // ✗ 错误

run(function () { ... })      // ✓ 正确
run(function() { ... })       // ✗ 错误
```

#### 展开运算符与它的表达式间不要留空白

```javascript
fn(...args); // ✗ 错误
fn(...args); // ✓ 正确
```

#### 遇到分号时空格要后留前不留

```javascript
for (let i = 0 ;i < items.length ;i++) {...}    // ✗ 错误
for (let i = 0; i < items.length; i++) {...}    // ✓ 正确
```

#### 代码块首尾留空格

```javascript
if (admin){...}     // ✗ 错误
if (admin) {...}    // ✓ 正确
```

#### 圆括号间不留空格

```javascript
getName(name); // ✗ 错误
getName(name); // ✓ 正确
```

#### 属性前面不要加空格

```javascript
user.name; // ✗ 错误
user.name; // ✓ 正确
```

#### 一元运算符前面跟一个空格

```javascript
typeof !admin; // ✗ 错误
typeof !admin; // ✓ 正确
```

#### 注释首尾留空格

```javascript
//comment           // ✗ 错误
// comment          // ✓ 正确

/*comment*/ // ✗ 错误
/* comment */ // ✓ 正确
```

#### 模板字符串中变量前后不加空格

```javascript
const message = `Hello, ${name}`; // ✗ 错误
const message = `Hello, ${name}`; // ✓ 正确
```

#### 逗号后面加空格

```javascript
// ✓ 正确
const list = [1, 2, 3, 4]
function greet (name, options) { ... }
```

```javascript
// ✗ 错误
const list = [1,2,3,4]
function greet (name,options) { ... }
```

#### 不允许有连续多行空行

```javascript
// ✓ 正确
const value = "hello world";
console.log(value);
```

```javascript
// ✗ 错误
const value = "hello world";

console.log(value);
```

#### 单行代码块两边加空格

```javascript
function foo() {
  return true;
} // ✗ 错误
function foo() {
  return true;
} // ✓ 正确
if (condition) {
  return true;
} // ✓ 正确
```

#### 不要使用非法的空白符

```javascript
function myFunc() /*<NBSP>*/ {} // ✗ 错误
```

#### 始终将逗号置于行末

```javascript
const obj = {
  foo: "foo",
  bar: "bar", // ✗ 错误
};

const obj = {
  foo: "foo",
  bar: "bar", // ✓ 正确
};
```

#### 点号操作符须与属性需在同一行

```javascript
console.log("hello"); // ✓ 正确

console.log("hello"); // ✗ 错误

console.log("hello"); // ✓ 正确
```

#### 文件末尾留一空行

#### 函数调用时标识符与括号间不留间隔

```javascript
console.log("hello"); // ✗ 错误
console.log("hello"); // ✓ 正确
```

#### 键值对当中冒号与值之间要留空白

```javascript
const obj = { key: "value" }; // ✗ 错误
const obj = { key: "value" }; // ✗ 错误
const obj = { key: "value" }; // ✗ 错误
const obj = { key: "value" }; // ✓ 正确
```

### 变量定义

#### 使用 const/let 定义变量

> 当前作用域不需要改变的变量使用 `const`，反之则使用 `let`

```javascript
const a = "a";
a = "b"; // ✗ 错误，请使用 let 定义

let test = "test";

var noVar = "hello, world"; // ✗ 错误，请使用 const/let 定义变量
```

#### 每个 const/let 关键字单独声明一个变量

```javascript
// ✓ 正确
const silent = true;
let verbose = true;

// ✗ 错误
const silent = true,
  verbose = true;

// ✗ 错误
let silent = true,
  verbose = true;
```

#### 不要重复声明变量

```javascript
let name = "John";
let name = "Jane"; // ✗ 错误

let name = "John";
name = "Jane"; // ✓ 正确
```

#### 不要使用 undefined 来初始化变量

```javascript
let name = undefined; // ✗ 错误

let name;
name = "value"; // ✓ 正确
```

#### 对于变量和函数名统一使用驼峰命名法

```javascript
function my_function() {} // ✗ 错误
function myFunction() {} // ✓ 正确

const my_var = "hello"; // ✗ 错误
const myVar = "hello"; // ✓ 正确
```

#### 不要定义未使用的变量

```javascript
function myFunction() {
  const result = something(); // ✗ 错误
}
```

#### 避免将变量赋值给自己

```javascript
name = name; // ✗ 错误
```

### 基本类型

#### 不要省去小数点前面的 0

```javascript
const discount = 0.5; // ✗ 错误
const discount = 0.5; // ✓ 正确
```

#### 字符串拼接操作符 (Infix operators) 之间要留空格

```javascript
// ✓ 正确
const x = 2;
const message = "hello, " + name + "!";
```

```javascript
// ✗ 错误
const x = 2;
const message = "hello, " + name + "!";
```

#### 不要使用多行字符串

```javascript
const message =
  "Hello \
                 world"; // ✗ 错误
```

#### 检查 NaN 的正确姿势是使用 isNaN()

```javascript
if (price === NaN) {
} // ✗ 错误
if (isNaN(price)) {
} // ✓ 正确
```

#### 用合法的字符串跟 typeof 进行比较操作

```javascript
typeof name === undefined; // ✗ 错误
typeof name === "undefined"; // ✓ 正确
```

### 对象与数组

#### 对象中定义了存值器，一定要对应的定义取值器

```javascript
const person = {
  set name(value) {
    // ✗ 错误
    this._name = value;
  },
};

const person = {
  set name(value) {
    this._name = value;
  },
  get name() {
    // ✓ 正确
    return this._name;
  },
};
```

#### 使用数组字面量而不是构造器

```javascript
const nums = new Array(1, 2, 3); // ✗ 错误
const nums = [1, 2, 3]; // ✓ 正确
```

#### 不要解构空值

```javascript
const {
  a: {},
} = foo; // ✗ 错误
const {
  a: { b },
} = foo; // ✓ 正确
```

#### 对象字面量中不要定义重复的属性

```javascript
const user = {
  name: "Jane Doe",
  name: "John Doe", // ✗ 错误
};
```

#### 不要扩展原生对象

```javascript
Object.prototype.age = 21; // ✗ 错误
```

#### 外部变量不要与对象属性重名

```javascript
let score = 100;
function game() {
  score: while (true) {
    // ✗ 错误
    score -= 10;
    if (score > 0) continue score;
    break;
  }
}
```

#### 对象属性换行时注意统一代码风格

```javascript
const user = {
  name: "Jane Doe",
  age: 30,
  username: "jdoe86", // ✗ 错误
};

const user = { name: "Jane Doe", age: 30, username: "jdoe86" }; // ✓ 正确

const user = {
  name: "Jane Doe",
  age: 30,
  username: "jdoe86",
};
```

#### 避免使用不必要的计算值作对象属性

```javascript
const user = { ["name"]: "John Doe" }; // ✗ 错误
const user = { name: "John Doe" }; // ✓ 正确
```

### 函数

#### 避免使用 arguments.callee 和 arguments.caller

```javascript
function foo(n) {
  if (n <= 0) return;

  arguments.callee(n - 1); // ✗ 错误
}

function foo(n) {
  if (n <= 0) return;

  foo(n - 1);
}
```

#### 不要定义冗余的函数参数

```javascript
function sum(a, b, a) {
  // ✗ 错误
  // ...
}

function sum(a, b, c) {
  // ✓ 正确
  // ...
}
```

#### 避免多余的函数上下文绑定

```javascript
const name = function () {
  getName();
}.bind(user); // ✗ 错误

const name = function () {
  this.getName();
}.bind(user); // ✓ 正确
```

#### 不要使用 eval()

```javascript
eval("var result = user." + propName); // ✗ 错误
const result = user[propName]; // ✓ 正确
```

#### 不要使用多余的括号包裹函数

```javascript
const myFunc = function () {}; // ✗ 错误
const myFunc = function () {}; // ✓ 正确
```

#### 避免对声明过的函数重新赋值

```javascript
function myFunc() {}
myFunc = myOtherFunc; // ✗ 错误
```

#### 注意隐式的 eval()

```javascript
setTimeout("alert('Hello world')"); // ✗ 错误
setTimeout(function () {
  alert("Hello world");
}); // ✓ 正确
```

#### 嵌套的代码块中禁止再定义函数

```javascript
if (authenticated) {
  function setAuthUser() {} // ✗ 错误
}
```

#### 禁止使用 Function 构造器

```javascript
const sum = new Function("a", "b", "return a + b"); // ✗ 错误
```

#### 禁止使用 Object 构造器

```javascript
let config = new Object(); // ✗ 错误
```

#### 自调用匿名函数 (IIFEs) 使用括号包裹

```javascript
const getName = (function () {})(); // ✗ 错误

const getName = (function () {})(); // ✓ 正确
const getName = (function () {})(); // ✓ 正确
```

#### 不使用 Generator 函数语法

> 使用 `Promise` 或者 `async functions` 来实现异步编程

```javascript
function* helloWorldGenerator() {
  // ✗ 错误
  yield "hello";
  yield "world";
  return "ending";
}
```

### 正则

#### 正则中避免使用多个空格

```javascript
const regexp = /test   value/; // ✗ 错误

const regexp = /test {3}value/; // ✓ 正确
const regexp = /test value/; // ✓ 正确
```

### 类定义

#### 类名要以大写字母开头

```javascript
class animal {}
const dog = new animal(); // ✗ 错误

class Animal {}
const dog = new Animal(); // ✓ 正确
```

#### 避免对类名重新赋值

```javascript
class Dog {}
Dog = "Fido"; // ✗ 错误
```

#### 子类的构造器中一定要调用 super

```javascript
class Dog {
  constructor() {
    super(); // ✗ 错误
  }
}

class Dog extends Mammal {
  constructor() {
    super(); // ✓ 正确
  }
}
```

#### 使用 this 前请确保 super() 已调用

```javascript
class Dog extends Animal {
  constructor() {
    this.legs = 4; // ✗ 错误
    super();
  }
}
```

#### 禁止多余的构造器

```javascript
class Car {
  constructor() {
    // ✗ 错误
  }
}

class Car {
  constructor() {
    // ✗ 错误
    super();
  }
}
```

#### 类中不要定义冗余的属性

```javascript
class Dog {
  bark() {}
  bark() {} // ✗ 错误
}
```

#### 无参的构造函数调用时要带上括号

```javascript
function Animal() {}
const dog = new Animal(); // ✗ 错误
const dog = new Animal(); // ✓ 正确
```

#### new 创建对象实例后需要赋值给变量

```javascript
new Character(); // ✗ 错误
const character = new Character(); // ✓ 正确
```

### 模块

#### 同一模块有多个导入时一次性写完

```javascript
import { myFunc1 } from "module";
import { myFunc2 } from "module"; // ✗ 错误

import { myFunc1, myFunc2 } from "module"; // ✓ 正确
```

#### import, export 和解构操作中，禁止赋值到同名变量

```javascript
import { config } from "./config"; // ✗ 错误
import { config } from "./config"; // ✓ 正确
```

### 语句

#### 避免在 return 语句中出现赋值语句

```javascript
function sum(a, b) {
  return (result = a + b); // ✗ 错误
}
```

#### 禁止使用 with

```javascript
with (val) {...}    // ✗ 错误
```

#### 不要使用标签语句

```javascript
label: while (true) {
  break label; // ✗ 错误
}
```

#### 不要随意更改关键字的值

```javascript
let undefined = "value"; // ✗ 错误
```

#### return，throw，continue 和 break 后不要再跟代码

```javascript
function doSomething() {
  return true;
  console.log("never called"); // ✗ 错误
}
```

### 逻辑与循环

#### 始终使用 === 替代 ==

> 例外： obj == null 可以用来检查 null || undefined

```javascript
if (name === 'John')   // ✓ 正确
if (name == 'John')    // ✗ 错误
```

```javascript
if (name !== 'John')   // ✓ 正确
if (name != 'John')    // ✗ 错误
```

#### 避免将变量与自己进行比较操作

```javascript
if (score === score) {
} // ✗ 错误
```

#### if/else 关键字要与花括号保持在同一行

```javascript
// ✓ 正确
if (condition) {
  // ...
} else {
  // ...
}
```

```javascript
// ✗ 错误
if (condition) {
  // ...
} else {
  // ...
}
```

#### 多行 if 语句的的括号不能省略

```javascript
// ✓ 正确
if (options.quiet !== true) console.log("done");
```

```javascript
// ✓ 正确
if (options.quiet !== true) {
  console.log("done");
}
```

```javascript
// ✗ 错误
if (options.quiet !== true) console.log("done");
```

#### 对于三元运算符 ? 和 : 与他们所负责的代码处于同一行

```javascript
// ✓ 正确
const location = env.development ? "localhost" : "www.api.com";

// ✓ 正确
const location = env.development ? "localhost" : "www.api.com";

// ✗ 错误
const location = env.development ? "localhost" : "www.api.com";
```

#### 请书写优雅的条件语句（avoid Yoda conditions）

```javascript
if (42 === age) {
} // ✗ 错误
if (age === 42) {
} // ✓ 正确
```

#### 避免使用常量作为条件表达式的条件（循环语句除外）

```javascript
if (false) {
  // ✗ 错误
  // ...
}

if (x === 0) {
  // ✓ 正确
  // ...
}

while (true) {
  // ✓ 正确
  // ...
}
```

#### 循环语句中注意更新循环变量

```javascript
for (let i = 0; i < items.length; j++) {...}    // ✗ 错误
for (let i = 0; i < items.length; i++) {...}    // ✓ 正确
```

#### 如果有更好的实现，尽量不要使用三元表达式

```javascript
let score = val ? val : 0; // ✗ 错误
let score = val || 0; // ✓ 正确
```

#### switch 语句中不要定义重复的 case 分支

```javascript
switch (id) {
  case 1:
  // ...
  case 1: // ✗ 错误
}
```

#### switch 一定要使用 break 来将条件分支正常中断

```javascript
switch (filter) {
  case 1:
    doSomething(); // ✗ 错误
  case 2:
    doSomethingElse();
}

switch (filter) {
  case 1:
    doSomething();
    break; // ✓ 正确
  case 2:
    doSomethingElse();
}

switch (filter) {
  case 1:
    doSomething();
  // fallthrough  // ✓ 正确
  case 2:
    doSomethingElse();
}
```

#### 避免不必要的布尔转换

```javascript
const result = true;
if (!!result) {
  // ✗ 错误
  // ...
}

const result = true;
if (result) {
  // ✓ 正确
  // ...
}
```

#### 避免使用逗号操作符

```javascript
if ((doSomething(), !!test)) {
} // ✗ 错误
```

### 错误处理

#### 不要丢掉异常处理中 err 参数

```javascript
// ✓ 正确
run(function (err) {
  if (err) throw err;
  window.alert("done");
});
```

```javascript
// ✗ 错误
run(function (err) {
  window.alert("done");
});
```

#### catch 中不要对错误重新赋值

```javascript
try {
  // ...
} catch (e) {
  e = "new value"; // ✗ 错误
}

try {
  // ...
} catch (e) {
  const newVal = "new value"; // ✓ 正确
}
```

#### 用 throw 抛错时，抛出 Error 对象而不是字符串

```javascript
throw "error"; // ✗ 错误
throw new Error("error"); // ✓ 正确
```

#### finally 代码块中不要再改变程序执行流程

```javascript
try {
  // ...
} catch (e) {
  // ...
} finally {
  return 42; // ✗ 错误
}
```

#### 使用 Promise 一定要捕捉错误

```javascript
asyncTask("google.com").catch((err) => console.log(err)); // ✓ 正确
```

## 组件及 JSX 书写规范

### 基本书写

#### 代码缩进

> 使用两个空格进行缩进，不要混合使用空格与制表符作为缩进

```javascript
class MyComponent extends Component {
  render() {
    return (
      <View className="test">
        {" "}
        // ✓ 正确
        <Text>12</Text> // ✗ 错误
      </View>
    );
  }
}
```

#### 单引号

> JSX 属性均使用双引号

```javascript
class MyComponent extends Component {
  render() {
    return (
      <View className="test">
        {" "}
        // ✓ 正确
        <Text className="test_text">12</Text> // ✗ 错误
      </View>
    );
  }
}
```

#### 对齐方式

> 多个属性，多行书写，每个属性占用一行，标签结束另起一行

```javascript
// bad
<Foo superLongParam='bar'
     anotherSuperLongParam='baz' />

// good
<Foo
  superLongParam='bar'
  anotherSuperLongParam='baz'
/>

// 如果组件的属性可以放在一行就保持在当前一行中
<Foo bar='bar' />

// 多行属性采用缩进
<Foo
  superLongParam='bar'
  anotherSuperLongParam='baz'
>
  <Quux />
</Foo>
```

#### 空格使用

> 终始在自闭合标签前面添加一个空格

```javascript
// bad
<Foo/>

// very bad
<Foo                 />

// bad
<Foo
 />

// good
<Foo />
```

#### 属性书写

> 属性名称始终使用驼峰命名法

```javascript
// bad
<Foo
  UserName='hello'
  phone_number={12345678}
/>

// good
<Foo
  userName='hello'
  phoneNumber={12345678}
/>
```

#### JSX 与括号

> 用括号包裹多行 JSX 标签

```javascript

// bad
render () {
  return <MyComponent className='long body' foo='bar'>
           <MyChild />
         </MyComponent>
}

// good
render () {
  return (
    <MyComponent className='long body' foo='bar'>
      <MyChild />
    </MyComponent>
  )
}

// good
render () {
  const body = <div>hello</div>
  return <MyComponent>{body}</MyComponent>
}
```

#### 标签

> 当标签没有子元素时，始终使用自闭合标签

```javascript
// bad
<Foo className='stuff'></Foo>

// good
<Foo className='stuff' />
```

> 如果控件有多行属性，关闭标签要另起一行

```javascript
// bad
<Foo
  bar='bar'
  baz='baz' />

// good
<Foo
  bar='bar'
  baz='baz'
/>
```

### 通用约束与建议

#### 所有内置组件均需要引入后再使用

```javascript
class MyComponent extends Component {
  render() {
    return (
      <View className="test">
        {" "}
        // ✓ 正确
        <Text>12</Text> // ✗ 错误
      </View>
    );
  }
}
```

#### 推荐使用对象解构的方式来使用 state、props

```javascript
class MyComponent extends Component {
  state = {
    myTime: 12,
  };
  render() {
    const { isEnable } = this.props; // ✓ 正确
    const { myTime } = this.state; // ✓ 正确
    return (
      <View className="test">
        {isEnable && <Text className="test_text">{myTime}</Text>}
      </View>
    );
  }
}
```

#### 不要在调用 this.setState 时使用 this.state

> 由于 this.setState 异步的缘故，这样的做法会导致一些错误，可以通过给 this.setState 传入函数来避免

```javascript
this.setState({
  value: this.state.value + 1,
}); // ✗ 错误

this.setState((prevState) => ({ value: prevState.value + 1 })); // ✓ 正确
```

#### map 循环时请给元素加上 key 属性

```javascript
list.map((item) => {
  return (
    <View className="list_item" key={item.id}>
      {item.name}
    </View>
  );
});
```

#### 尽量避免在 componentDidMount 中调用 this.setState

> 因为在 `componentDidMount` 中调用 `this.setState` 会导致触发更新

```javascript
class MyComponent extends Component {
  state = {
    myTime: 12,
  };

  componentDidMount() {
    this.setState({
      // ✗ 尽量避免，可以在 componentWillMount 中处理
      name: 1,
    });
  }

  render() {
    const { isEnable } = this.props;
    const { myTime } = this.state;
    return (
      <View className="test">
        {isEnable && <Text className="test_text">{myTime}</Text>}
      </View>
    );
  }
}
```

#### 不要在 componentWillUpdate/componentDidUpdate/render 中调用 this.setState

```javascript
class MyComponent extends Component {
  state = {
    myTime: 12,
  };

  componentWillUpdate() {
    this.setState({
      // ✗ 错误
      name: 1,
    });
  }

  componentDidUpdate() {
    this.setState({
      // ✗ 错误
      name: 1,
    });
  }

  render() {
    const { isEnable } = this.props;
    const { myTime } = this.state;
    this.setState({
      // ✗ 错误
      name: 11,
    });
    return (
      <View className="test">
        {isEnable && <Text className="test_text">{myTime}</Text>}
      </View>
    );
  }
}
```

#### 不要定义没有用到的 state

```javascript
class MyComponent extends Component {
  state = {
    myTime: 12,
    noUsed: true, // ✗ 没有用到
  };

  render() {
    const { myTime } = this.state;
    return (
      <View className="test">
        <Text className="test_text">{myTime}</Text>
      </View>
    );
  }
}
```

#### 组件最好定义 defaultProps

```javascript
class MyComponent extends Component {
  static defaultProps = {
    isEnable: true,
  };

  state = {
    myTime: 12,
  };

  render() {
    const { isEnable } = this.props;
    const { myTime } = this.state;

    return (
      <View className="test">
        {isEnable && <Text className="test_text">{myTime}</Text>}
      </View>
    );
  }
}
```
