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

- **Error, Never Warn:** Warnings are noise and get ignored. Either it's an issue, or it isn't. This config forces developers to fix problems or explicitly disable the rule with a comment.
- **Strict, Consistent Code Style:** When multiple approaches exist, this configuration enforces the strictest, most consistent code style, preferring modern language features and best practices.
- **Prevent Bugs:** Problematic patterns such as `instanceof` are not allowed, forcing developers to choose more robust patterns. Debug-only code such as `console.log` or `test.only` are disallowed to avoid accidental CI failures or unintended logging in production.
- **Fast:** Slow rules are avoided. For example, TypeScript's `noUnusedLocals` check is preferred over `no-unused-vars`.
- **Don't get in the way:** [Subjective or overly opinionated rules](https://github.com/airbnb/javascript) (e.g. style preferences) are disabled. Autofixable rules are preferred to reduce friction and save time.

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
