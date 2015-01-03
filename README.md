# LSON: LiveScript Object Notation Parser

Same API as the JSON or CSON modules, but for [LiveScript](http://livescript.net/) objects. Also supports CSON and JSON (since LSON is a superset of them).

Uses the LiveScript parser to do the actual parsing. Will not execute code.

## Install

    npm install lson

## API

lson.parse: Given a string, outputs an object.

lson.stringify: Given an object, outputs a string. Currently outputs pretty-printed JSON.

## Example

```livescript
lson = require('lson')

parsed = lson.parse('''
an_array: <[ an array of strings ]>
another_array: [
  'another'
  'array'
]
# we can even have comments
a_dict: {
  key: 'value'
}
a_string: 'some string'
another_string: \\anotherstring
''')

console.log(lson.stringify(parsed))
/*
{
  "an_array": [
    "an",
    "array",
    "of",
    "strings"
  ],
  "another_array": [
    "another",
    "array"
  ],
  "a_dict": {
    "key": "value"
  },
  "a_string": "some string",
  "another_string": "anotherstring"
}
*/
```

## Licence

MIT

## Credits

Author: [Geza Kovacs](https://github.com/gkovacs)
