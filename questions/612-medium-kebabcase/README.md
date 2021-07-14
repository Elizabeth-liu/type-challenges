<!--info-header-start--><h1>KebabCase <img src="https://img.shields.io/badge/-medium-d9901a" alt="medium"/> <img src="https://img.shields.io/badge/-%23template--literal-999" alt="#template-literal"/></h1><blockquote><p>by Johnson Chu <a href="https://github.com/johnsoncodehk" target="_blank">@johnsoncodehk</a></p></blockquote><p><a href="https://tsch.js.org/612/play" target="_blank"><img src="https://img.shields.io/badge/-Take%20the%20Challenge-3178c6?logo=typescript&logoColor=white" alt="Take the Challenge"/></a> </p><!--info-header-end-->

`FooBarBaz` -> `for-bar-baz`

```ts
没懂
type TransformUppercaseLetter<S extends string> = 
  S extends `${infer L}${infer R}` 
  ? (
    L extends Lowercase<L> 
    ? `${L}${TransformUppercaseLetter<R>}`
    : `-${Lowercase<L>}${TransformUppercaseLetter<R>}`
  ) 
  : S;
type HandleFirst<S extends string> = S extends `${infer L}${infer R}` ? `${Lowercase<L>}${R}` : S
type KebabCase<S extends string> = TransformUppercaseLetter<HandleFirst<S>>
```ts


<!--info-footer-start--><br><a href="../../README.md" target="_blank"><img src="https://img.shields.io/badge/-Back-grey" alt="Back"/></a> <a href="https://tsch.js.org/612/answer" target="_blank"><img src="https://img.shields.io/badge/-Share%20your%20Solutions-teal" alt="Share your Solutions"/></a> <a href="https://tsch.js.org/612/solutions" target="_blank"><img src="https://img.shields.io/badge/-Check%20out%20Solutions-de5a77?logo=awesome-lists&logoColor=white" alt="Check out Solutions"/></a> <!--info-footer-end-->
