# JavaScript 开发规范

**用更合理的方式写 JavaScript**

<a name="table-of-contents"></a>
## 目录

  1. [类型](#types)
  2. [引用](#references)

<a name="types"></a>
## 类型

  - [1.1](#1.1) <a name='1.1'></a> **基本类型**: 直接存取基本类型。

    + `字符串`
    + `数值`
    + `布尔类型`
    + `null`
    + `undefined`

    ```javascript
    const foo = 1;
    let bar = foo;

    bar = 9;

    console.log(foo, bar); // => 1, 9
    ```

  - [1.2](#1.2) <a name='1.2'></a> **复杂类型**: 通过引用的方式存取复杂类型。

    + `对象`
    + `数组`
    + `函数`

    ```javascript
    const foo = [1, 2];
    const bar = foo;

    bar[0] = 9;

    console.log(foo[0], bar[0]); // => 9, 9
    ```

**[⬆ 返回目录](#table-of-contents)**

<a name="references"></a>
## 引用
