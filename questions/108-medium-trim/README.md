<!--info-header-start--><h1>Trim <img src="https://img.shields.io/badge/-medium-d9901a" alt="medium"/> <img src="https://img.shields.io/badge/-%23template--literal-999" alt="#template-literal"/></h1><blockquote><p>by Anthony Fu <a href="https://github.com/antfu" target="_blank">@antfu</a></p></blockquote><p><a href="https://tsch.js.org/108/play" target="_blank"><img src="https://img.shields.io/badge/-Take%20the%20Challenge-3178c6?logo=typescript&logoColor=white" alt="Take the Challenge"/></a> &nbsp;&nbsp;&nbsp;<a href="./README.ja.md" target="_blank"><img src="https://img.shields.io/badge/-%E6%97%A5%E6%9C%AC%E8%AA%9E-gray" alt="日本語"/></a> </p><!--info-header-end-->

Implement `Trim<T>` which takes an exact string type and returns a new string with the whitespace from both ends removed.

For example

```ts
type trimed = Trim<'  Hello World  '> // expected to be 'Hello World'


解答：

1. type Trim<S extends string> = S extends `${' '|'\n'|'\t'}${infer F}` ? Trim<F> : S extends `${infer F}${' '|'\n'|'\t'}` ? Trim<F> : S;

2. type Space = ' ' | '\t' | '\n';
   type Trim<S extends string> = S extends `${Space}${infer T}` | `${infer T}${Space}` ? Trim<T> : S;

```


<!--info-footer-start--><br><a href="../../README.md" target="_blank"><img src="https://img.shields.io/badge/-Back-grey" alt="Back"/></a> <a href="https://tsch.js.org/108/answer" target="_blank"><img src="https://img.shields.io/badge/-Share%20your%20Solutions-teal" alt="Share your Solutions"/></a> <a href="https://tsch.js.org/108/solutions" target="_blank"><img src="https://img.shields.io/badge/-Check%20out%20Solutions-de5a77?logo=awesome-lists&logoColor=white" alt="Check out Solutions"/></a> <!--info-footer-end-->
