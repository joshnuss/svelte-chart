## Stuff that need attention

### First `npm i`

```sh
$ npm i
npm WARN deprecated urix@0.1.0: Please see https://github.com/lydell/urix#deprecated
npm WARN deprecated resolve-url@0.2.1: https://github.com/lydell/resolve-url#deprecated
npm WARN deprecated sourcemap-codec@1.4.6: Please use @jridgewell/sourcemap-codec instead
npm WARN deprecated source-map-url@0.4.0: See https://github.com/lydell/source-map-url#deprecated
npm WARN deprecated rollup-plugin-node-resolve@5.2.0: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-node-resolve.
npm WARN deprecated chokidar@2.1.8: Chokidar 2 does not receive security updates since 2019. Upgrade to chokidar 3 with 15x fewer dependencies
npm WARN deprecated source-map-resolve@0.5.2: See https://github.com/lydell/source-map-resolve#deprecated
npm WARN deprecated rollup-plugin-terser@5.1.2: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-terser
npm WARN deprecated rollup-plugin-commonjs@10.1.0: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-commonjs.

added 199 packages, and audited 200 packages in 11s

1 package is looking for funding
  run `npm fund` for details

12 vulnerabilities (1 low, 3 moderate, 8 high)
```

### `npm ci` after `npm audit fix`

```sh
$ npm ci
npm WARN deprecated rollup-plugin-terser@5.3.1: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-terser
npm WARN deprecated sourcemap-codec@1.4.6: Please use @jridgewell/sourcemap-codec instead
npm WARN deprecated rollup-plugin-node-resolve@5.2.0: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-node-resolve.
npm WARN deprecated rollup-plugin-commonjs@10.1.0: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-commonjs.

added 73 packages, and audited 74 packages in 718ms

4 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
```