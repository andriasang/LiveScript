# Coco
is a [CoffeeScript](http://coffeescript.org) dialect that aims to be more radical and practical.

## Principles
- Respect JavaScript/ECMAScript semantics, but supply ways to amend them.
- Reserve less keywords.
- Die for [DRY](http://en.wikipedia.org/wiki/Don%27t_repeat_yourself).
- Performance over readability.
- Readability over compressability.

## Features
- [Additions](https://github.com/satyr/coco/wiki/additions)
- [Improvements](https://github.com/satyr/coco/wiki/improvements)

## Incompatibilities

### behavior
- Assigning to a variable with `=` declares it on the _current_ scope. Use `:=` to modify variables declared on upper scopes.
- The roles of `in` and `of` have been swapped to keep the JS semantics.
- The range syntax (_x..y_) is removed.
- `===`/`!==`/`==`/`!=` each compiles as is.
- `...` is prefix.
- `super` represents the direct reference to the parent function rather than being a call. Use `super ...` (just `super` in Coffee) for a simple delegation.
- Nested comprehensions returns flattened results.

### keyword
- _yes_/_no_/_on_/_off_ are not reserved. Define your own or just use `true`/`false`.
- _undefined_ is not reserved.
- `switch`-`case`-`default` replaces `switch`-_when_-`else`.
- `for ever` replaces _loop_.
- _when_ is removed. Write `a if b while c` instead of `a while c when b`.

### other
- The binaries are named __coco__ and __coke__ (to coexist with _coffee_ and _cake_).

## Installation
Install [node.js](http://nodejs.org), then

    git clone git:github.com/satyr/coco.git && cd coco && bin/coke install

Or install [npm](https://github.com/isaacs/npm#readme), then

    npm install coco


## Help

    coco -h; coke

## Changelog

### 0.1.5
- Conditional control structures can now be anaphoric;
  `that` within `if`, `while` or `case` block now refers to the condition value.
- Decimal numbers can now have arbitrary trailing alphabets as comments.
  e.g. `9times`, `1.5s`
- Added `<<<`/`<<<<` as aliases to `import`/`import all`
- non-ASCII identifiers are now allowed.

### 0.1.4
- `.` and its families can now be used with numbers and strings, instead of `[]`.
  `a.0.'0'` compiles to `a[0]['0']`.
- Added syntax for cloning objects;
  `obj{key:val}` acts like a simple version of ES5 `Object.create`,
  creating a prototypal child of `obj` and assigning to `.key` with `val`.
- default arguments can now choose to use `||`/`&&`.
- `super` under a class block now refers to the superclass.
- _.coffee_ extension is no longer supported.

### 0.1.3
- Compilation now prefers single quotes.
- AST now compiles faster, roughly 1.4 times than 0.1.2.
- `[]`/`{}` can now be safely used as an placeholder within array destructuring.
- Improved `--nodes` output.

### 0.1.2
- `...` is now prefix.
- `{0: first, (*-1): last} = array` now works.
- Added `--lex` to the `coco` utility. Removed `--lint`.
- _src/_ now has [doc view](http://satyr.github.com/coco/src/).

### 0.1.1
Release.
