<!--info-header-start--><h1>Includes <img src="https://img.shields.io/badge/-easy-7aad0c" alt="easy"/> <img src="https://img.shields.io/badge/-%23array-999" alt="#array"/></h1><blockquote><p>by null <a href="https://github.com/kynefuk" target="_blank">@kynefuk</a></p></blockquote><p><a href="https://tsch.js.org/898/play" target="_blank"><img src="https://img.shields.io/badge/-Take%20the%20Challenge-3178c6?logo=typescript&logoColor=white" alt="Take the Challenge"/></a> </p><!--info-header-end-->

Implement the JavaScript `Array.includes` function in the type system. A type takes the two arguments. The output should be a boolean `true` or `false`.

For example

```ts
type isPillarMen = Includes<['Kars', 'Esidisi', 'Wamuu', 'Santana'], 'Dio'> // expected to be `false`


解答：
type Includes<T extends readonly any[], U> = U extends T[number] ? true : false;


别人的答案：
//看不懂......
type MyEqual<X, Y> = (<T>() => T extends X ? 1 : 2 ) extends (<T>() => T extends Y ? 1 : 2) ? true : false

type Includes<T extends readonly any[], U> = true extends {
  [I in keyof T]: MyEqual<T[I], U>
}[number] ? true : false
```


<!--info-footer-start--><br><a href="../../README.md" target="_blank"><img src="https://img.shields.io/badge/-Back-grey" alt="Back"/></a> <a href="https://tsch.js.org/898/answer" target="_blank"><img src="https://img.shields.io/badge/-Share%20your%20Solutions-teal" alt="Share your Solutions"/></a> <a href="https://tsch.js.org/898/solutions" target="_blank"><img src="https://img.shields.io/badge/-Check%20out%20Solutions-de5a77?logo=awesome-lists&logoColor=white" alt="Check out Solutions"/></a> <!--info-footer-end-->
