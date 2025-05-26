# `@nkzw/eslint-config`

Opinionated ESLint config with sensible defaults.

## Installation & Usage

With ESLint v9+:

```
npm install @nkzw/eslint-config
```

In your `eslint.config.js`:

```js
import nkzw from '@nkzw/eslint-config';

export default nkzw;
```

Or, if you have custom ESLint rules or configuration:

```js
import nkzw from '@nkzw/eslint-config';

export default [
  ...nkzw,
  {
    // Custom configuration.
  },
];
```

Then run `pnpm eslint .` or `npm eslint .`.

_Note: You can use @nkzw/eslint-config 1.x with ESLint versions 8 and below._

## Philosophy & Principles

Use this configuration if these principles resonate with you:

- **Error, Never Warn:** People tend to ignore warnings. There is little value in only warning about potentially problematic code patterns. Either it's an issue or not. Errors force the developer to address the problem either by fixing it or explicitly disabling the role in that location.
- **Strict, consistent code style:** If there are multiple ways of doing something, or there is a new language construct or best practice, this configuration will suggest the most strict and consistent solution.
- **Prevent Bugs:** Problematic patterns such as `instanceof` are not allowed. This forces developers to choose more robust patterns. This configuration disallows usage of `console` or `test.only` so that you don't end up with unintended logging in production or CI failures. If you want to log to the console in your production app, use another function that calls `console.log` to distinguish between debug logs and intentional logs.
- **Fast:** Slow rules are avoided if possible. For example, it is recommended to use the fast `noUnusedLocals` check in TypeScript instead of the `no-unused-vars` rules.
- **Don't get in the way:** Rules that get in the way or are too [subjective](https://github.com/airbnb/javascript) are disabled. Rules with autofixers are preferred over rules without them.

## Included Plugins & Rules

This configuration consists of the most useful and least annoying rules from the following eslint plugins:

- [`typescript-eslint`](https://github.com/typescript-eslint/typescript-eslint)
- [`eslint-import-resolver-typescript`](https://www.npmjs.com/package/eslint-import-resolver-typescript)
- [`eslint-plugin-unicorn`](https://github.com/sindresorhus/eslint-plugin-unicorn)
- [`eslint-plugin-import-x`](https://github.com/un-ts/eslint-plugin-import-x)
- [`eslint-plugin-react`](https://github.com/jsx-eslint/eslint-plugin-react)
- [`eslint-plugin-react-hooks`](https://github.com/facebook/react/tree/main/packages/eslint-plugin-react-hooks)
- [`eslint-plugin-perfectionist`](https://perfectionist.dev/)
- [`eslint-plugin-no-instanceof`](https://www.npmjs.com/package/eslint-plugin-no-instanceof)
- [`eslint-plugin-no-only-tests`](https://github.com/levibuzolic/eslint-plugin-no-only-tests)

## Suggestions

This configuration is meant to be used with:

- [TypeScript](https://www.typescriptlang.org/) and the [`noUnusedLocals`](https://www.typescriptlang.org/tsconfig#noUnusedLocals) setting.
- [Prettier](https://prettier.io/) and the [`@ianvs/prettier-plugin-sort-imports`](https://github.com/ianvs/prettier-plugin-sort-imports).

Read about more [frontend tooling suggestions in this blog post](https://cpojer.net/posts/fastest-frontend-tooling-in-2022).
