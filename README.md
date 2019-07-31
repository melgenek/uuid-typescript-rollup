```
index.ts → output.js...
(!) Plugin node-resolve: preferring built-in module 'crypto' over local alternative at 'crypto', pass 'preferBuiltins: false' to disable this behavior or 'preferBuiltins: true' to disable this warning
(!) Unresolved dependencies
https://rollupjs.org/guide/en/#warning-treating-module-as-external-dependency
crypto (imported by node_modules/uuid/lib/rng.js, crypto?commonjs-external)
(!) Missing global variable name
Use output.globals to specify browser global variable names corresponding to external modules
crypto (guessing 'crypto')
created output.js in 143ms
```

Rollup does not take into account the `browser` value from `package.json` into account https://github.com/kelektiv/node-uuid/blob/master/package.json#L36

It uses https://github.com/kelektiv/node-uuid/blob/master/lib/rng.js instead of https://github.com/kelektiv/node-uuid/blob/master/lib/sha1-browser.js
