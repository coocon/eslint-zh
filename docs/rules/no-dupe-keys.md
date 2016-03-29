---
title: Rule no-dupe-keys
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->

# Disallow Duplicate Keys (no-dupe-keys)

Creating objects with duplicate keys in objects can cause unexpected behavior in your application. The `no-dupe-keys` rule flags the use of duplicate keys in object literals.

```js
var foo = {
    bar: "baz",
    bar: "qux"
};
```

## Rule Details

This rule is aimed at preventing possible errors and unexpected behavior that might arise from using duplicate keys in object literals. As such, it warns whenever it finds a duplicate key.

Examples of **incorrect** code for this rule:

```js
/*eslint no-dupe-keys: "error"*/

var foo = {
    bar: "baz",
    bar: "qux"
};

var foo = {
    "bar": "baz",
    bar: "qux"
};

var foo = {
    0x1: "baz",
    1: "qux"
};
```

Examples of **correct** code for this rule:

```js
/*eslint no-dupe-keys: "error"*/

var foo = {
    bar: "baz",
    quxx: "qux"
};
```

## Version

This rule was introduced in ESLint 0.0.9.

## Resources

* [Rule source](https://github.com/eslint/eslint/tree/master/lib/rules/no-dupe-keys.js)
* [Documentation source](https://github.com/eslint/eslint/tree/master/docs/rules/no-dupe-keys.md)
