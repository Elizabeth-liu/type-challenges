<!--info-header-start--><h1>Camelize <img src="https://img.shields.io/badge/-hard-de3d37" alt="hard"/> <img src="https://img.shields.io/badge/-%23union-999" alt="#union"/> <img src="https://img.shields.io/badge/-%23recursion-999" alt="#recursion"/></h1><blockquote><p>by Denis <a href="https://github.com/denchiklut" target="_blank">@denchiklut</a></p></blockquote><p><a href="https://tsch.js.org/1383/play" target="_blank"><img src="https://img.shields.io/badge/-Take%20the%20Challenge-3178c6?logo=typescript&logoColor=white" alt="Take the Challenge"/></a> </p><!--info-header-end-->

Implement Camelize which converts object from snake_case to to camelCase

```ts
Camelize<{
  some_prop: string, 
  prop: { another_prop: string },
  array: [{ snake_case: string }]
}>

// expected to be
// {
//   someProp: string, 
//   prop: { anotherProp: string },
//   array: [{ snakeCase: string }]
// }
```

```ts
/**
 * SnakeToCapitalizeCamel<'foo'> = 'Foo'.
 * SnakeToCapitalizeCamel<'foo_bar'> = `FooBar'.
 */
type SnakeToCapitalizeCamel<S extends string> = S extends `${infer Word}_${infer Rest}`
    ? `${Capitalize<Word>}${SnakeToCapitalizeCamel<Rest>}`
    : Capitalize<S>;

/**
 * SnakeToCamel<'foo'> = 'foo'.
 * SnakeToCamel<'foo_bar'> = 'fooBar'.
 */
type SnakeToCamel<S> = S extends `${infer Word}_${infer Rest}`
    ? `${Word}${SnakeToCapitalizeCamel<Rest>}`
    : S;

type Camelize<T> = {
    [K in keyof T as SnakeToCamel<K>]: Camelize<T[K]>;
};
```ts

<!--info-footer-start--><br><a href="../../README.md" target="_blank"><img src="https://img.shields.io/badge/-Back-grey" alt="Back"/></a> <a href="https://tsch.js.org/1383/answer" target="_blank"><img src="https://img.shields.io/badge/-Share%20your%20Solutions-teal" alt="Share your Solutions"/></a> <a href="https://tsch.js.org/1383/solutions" target="_blank"><img src="https://img.shields.io/badge/-Check%20out%20Solutions-de5a77?logo=awesome-lists&logoColor=white" alt="Check out Solutions"/></a> <!--info-footer-end-->
