# tsup-bundle-playground

The repo has 2 packages: "a" and "b". Package "a" depends on "b". We want to bundle package "b" inside of the package "a".


In order to do so we run:

```
yarn workspace a tsup ./src/index.ts --dts
```

or even

```
yarn workspace a tsup ./src/index.ts --dts --dts-resolve
```

but the dist/index.d.ts still refers to the package "b" which doesn't exist.

```ts
export { getMessage } from 'b';
```
