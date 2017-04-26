# JavaScript Code Style

ES6, 11-12am

## ES6

https://github.com/airbnb/javascript#ecmascript-6-es-2015-styles

## code style

- prefer const/let. prefer-const, no-const-assign
- dynamic property name: `Object = {[getKey()]: value, key: value}`. object-shorthand
- method shorthand. object-shorthand
- property value shorthand. object-shorthand
- only quote properties that are invalid indentifers. quote-props
- prefer `Object.assign`
- spreads `...` to copy arrays
- prefer import/export
- Array.from
- arrow function
    + `()`, `return` and `{}` when multiple lines
    + none of them when single line
    + Use line breaks after open and before close array brackets if an array has multiple lines
- destructuring
- template literals for interpolation and newlines
- use `...` instead of arguments
- default function argument value and put them last


- arrow function () wrap object and In case the expression spans over multiple lines, wrap it in parentheses for better readability.
- If your function takes a single argument and doesn’t use braces, omit the parentheses. Otherwise, always include parentheses around arguments for clarity and consistency.
    ~~~JavaScript
    /*eslint arrow-parens: ["error", "as-needed"]*/
    /*eslint-env es6*/

    () => {};
    a => {};
    a => a;
    a => {'\n'};
    a.then(foo => {});
    a.then(foo => { if (true) {} });
    (a, b, c) => a;
    (a = 10) => a;
    ([a, b]) => a;
    ({a, b}) => a;
    ~~~
- Avoid confusing arrow function syntax (=>) with comparison operators (<=, >=)
    ~~~JavaScript
    // bad
    const itemHeight = item => item.height > 256 ? item.largeSize : item.smallSize;

    // bad
    const itemHeight = (item) => item.height > 256 ? item.largeSize : item.smallSize;

    // good
    const itemHeight = item => (item.height > 256 ? item.largeSize : item.smallSize);

    // good
    const itemHeight = (item) => {
      const { height, largeSize, smallSize } = item;
      return height > 256 ? largeSize : smallSize;
    };
    ~~~
- Although the one-liner is concise, having one clear way to import and one clear way to export makes things consistent.
    ~~~
    // bad
    // filename es6.js
    export { es6 as default } from './AirbnbStyleGuide';

    // good
    // filename es6.js
    import { es6 } from './AirbnbStyleGuide';
    export default es6;
    ~~~
- import from a path in one place
    ~~~JS
    // bad
    import foo from 'foo';
    // … some other imports … //
    import { named1, named2 } from 'foo';

    // good
    import foo, { named1, named2 } from 'foo';

    // good
    import foo, {
      named1,
      named2,
    } from 'foo';
    ~~~


- Use braces to create blocks in case and default clauses that contain lexical declarations
- Ternaries should not be nested and generally be single line expressions.
- `if` always multiple lines with `{}`
- start all comments with a space


- `//` for single line, `/** .. */` for multiple line
- use `// FIXME: ` to annotate problems
- use `// TODO: ` to annotate solutions to problems

- function [name](){}; the space is important
- 2 spaces
- 1 space before the leading brace
- 1 space before the opening parenthesis in control statements. requireSpaceAfterKeywords
- operators with spaces
- end files with a single newline
- use indentation when making long method chains. use leading dot
- leave a blank line after blocks and before the next statement
- not pad your blocks with blank lines
- no spaces inside parenthese, brackets, braces


- less 100 characters per line
- trailing commas, no leading commas // good for diff, easy to write, easy to read
- always simecomma ends
- single quote
- IIFE is a single unit. (function(){}())
- multiple arguments
    ~~~JavaScript
    function foo(
        bar,
        baz
    ) {}
    ~~~
- no ++/--
- ===/!==


- not Broken strings, painful
- use function expression instead of function delarations because of function hoisting which harms readability and maintainability. ???
- dont mutate or reassign parameters if possible.
- return this is ok.
- prefer Use map() / every() / filter() / find() / findIndex() / reduce() / some() / ... to iterate over arrays, and Object.keys() / Object.values() / Object.entries() to produce arrays so you can iterate over objects.
- use const/let per variable
- don't chain variable assignments

- Use shortcuts for booleans, but explicit comparisons for strings and numbers.
- perform type coercion at the beginning of the statement
- String(xxx)
- Number(xxx) or parseInt(xxx, radix) with radix always.
- Boolean(age)/!!age

- camelCase for variable, PascalCase Constructors or classes
- no underscore dangle???
- use arrow function or Function#bind instead of save references
- the base filename should exactly match the name of its default export
- use camelCase for function, PascalCase for constructor/class/singleton/functionlibrary/bare object
- Acronyms and initialisms should always be all capitalized or all lowercased
- no setter/getter is possible
- attaching data payloads to events with a hash instead of a row value
- prefix jQuery object variables with a  `$`
- postfix Stream object variables with a `$`
- cache jQuery lookup
- error first callback
- improve nested conditional

## eslint

is a tool for identifying and reporting on patterns found in ECMAScript/JavaScript code, with the goal of making code more consistent and avoiding bugs

### install

npm i [-g] eslint
eslint --init
eslint js


### formatter

`-f, --format`
json
tap
html


### .eslintrc

root
parserOptions
    ecmaVerson
    sourceType
    ecmaFeatures
        globalReturn
        impliedStrict
        jsx
        experimentalObjectRestSpread
env
parser
globals  /* global var1:false, var2 */
settings
plugins
extends
rules
    rule: 'off'|warn-level|[warn-level, value, optsForRul]


### .eslintignore


### disable and enable in code

Environments - which environments your script is designed to run in. Each environment brings with it a certain set of predefined global variables.
Globals - the additional global variables your script accesses during execution.
Rules - which rules are enabled and at what error level.

/* eslint-disable|enable  [rule, rule...] */
// eslint-disable-next-line  [rule, rule...]
// eslint-disable-line [rule, rule...]

### configure rules

/* eslint [rule] */


## Resources

https://github.com/airbnb/javascript
http://coolshell.cn/articles/17757.html
http://eslint.org/docs/user-guide/configuring