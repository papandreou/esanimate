esanimate
=========

Convert back and forth between esprima/SpiderMonkey ASTs and JavaScript objects.

Example:

```js
require('esanimate').astify({ foo: 'bar', quux: 123 });
```

Returns:

```javascript
{ type: 'ObjectExpression',
  properties:
   [ { kind: 'init',
       key: { type: 'Identifier', name: 'foo' },
       value: { type: 'Literal', value: 'bar' } },
     { kind: 'init',
       key: { type: 'Identifier', name: 'quux' },
       value: { type: 'Literal', value: 123 } } ] }
```

And the other way around:

```javascript
esanimate.objectify({
    type: 'ObjectExpression',
    properties: [
        {
            kind: 'init',
            key: { type: 'Identifier', name: 'foo' },
            value: { type: 'Literal', value: 'bar' }
        }
    ]
});
```

Output:
```
{ foo: 'bar' }
```

License
-------

3-clause BSD license -- see the `LICENSE` file for details.
