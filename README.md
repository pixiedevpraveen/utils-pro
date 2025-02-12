# utiljs-pro
![Package Size](https://deno.bundlejs.com/badge?q=utiljs-pro)
[![JSR](https://jsr.io/badges/@praveen/utiljs-pro)](https://jsr.io/@praveen/utiljs-pro)
[![JSR Score](https://jsr.io/badges/@praveen/utiljs-pro/score)](https://jsr.io/@praveen/utiljs-pro/score)


TypeScript friendly Utility functions for Developers.

To install:

```bash
# npm
npm install utiljs-pro

# bun
bun add utiljs-pro

# yarn
yarn add utiljs-pro

# pnpm
pnpm add utiljs-pro

# CDN
https://unpkg.com/utiljs-pro@1.0.0/build/index.js
```


```ts
// isPromise
const promise = new Promise(res => setTimeout(() => res(1), 50)) as Promise<number> | number

if (isPromise(obj)) { // true
    obj; // hovering on obj shows the type as Promise<number>
    const d = await obj; // now hovering on d shows the type as number
} else {
    obj; // hovering on obj shows the type as number
}

```


```ts
// isAsyncFunction
const asyncFn = (async () => { }) as unknown as (() => Promise<number>) | (() => number)
if (isAsyncFunction<number, () => Promise<number>>(asyncFn)) { // true
    const p = asyncFn(); // hovering on function shows the type as (() => Promise<number>) and on p as Promise<number>
    const d = await p; // now hovering on d shows the type as Promise<number>
} else {
    const d = asyncFn(); // hovering on function shows the type as (() => number) and on d as number
}
```
