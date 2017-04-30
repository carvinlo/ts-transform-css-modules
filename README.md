# ts-transform-css-modules-transform
Extract css class names from required css module files for TypeScript. This plugin is based on [css-modules-require-hook](https://github.com/css-modules/css-modules-require-hook) and so constructor opts are from that repo.

This allows you to do this in TS files:

```ts
// Import works
import * as css from 'foo.css'
// require also works
const foo = require('foo.css')

console.log(css.foo)
```

Append this to `before` in your compilation step. See [compile.ts](./compile.ts) for more info.

Right now named imports will not work due to TS mangling import name after compilation.

```ts
// Those are NOT working
import css from 'foo.css'
import { button, badge } from 'foo.css'
```

## Options

See [css-modules-require-hook](https://github.com/css-modules/css-modules-require-hook#tuning-options) for a list of options.