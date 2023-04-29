# angular-best-practice

## Creating Angular Libraries

- First create the DEMO project
   - `ng new my-lib-demo --routing true --style scss && cd my-lib-demo`
- Create the library
   - `ng generate library my-lib`

## Code style
- Create separate directories for modules and elements in src/app
- Routable components should NOT be standalone, but reusable ui-elements should be
- Use change-detector-strategy onPush
- Use self-closing tags
- Use view encapsulation None, create a wrapper using `@HostBinding() class = 'app-demo-component'`

## Add basic packages

```sh
ng add @angular/material
ng add @angular-eslint/schematics
ng add @ngx-pwa/local-storage

npm i -S normalize.css ngx-md-icon @mdi/js mat-icon-button-sizes \
moment-mini@github:ksloan/moment-mini lodash-es change-case-all \
await-to-js ngx-modern-alerts
```

## eslint plugins

Copy `.eslintrc.js` to your project

```sh
npm i -D eslint-plugin-decorator-position eslint-plugin-jsdoc
```

## prettier plugins

Copy `.prettierrc` to your project

```sh
npm i -D prettier prettier-plugin-organize-imports prettier-plugin-packagejson
```

## Git protect main branch
Copy `hooks` directory to your project<br>
Add the following to your `package.json`

```json
"preinstall": "git config core.hooksPath hooks",
```

## Update package.json version and build

Copy `environments/before-build.js` to your project<br>
Add the following to your `package.json`

```json
"format-prettier": "prettier --loglevel warn --write \"./src/**/*.{ts,scss,json}\"",
```

## Firefox based e2e tests

Copy `karma.conf.js` to your project

```sh
npm i -D karma-firefox-launcher
```

Add the following to your `package.json`

```json
"test": "ng test",
"test:ci": "ng test --no-watch --no-progress --browsers=FirefoxHeadless",
```

## Bundle Analyzer

```sh
npm i -D webpack-bundle-analyzer
```

Add the following to your `package.json`

```json
"bundle-report": "webpack-bundle-analyzer dist/ims-frontend/stats.json",
```

## Disable live reload

Recommendable for large projects
Add the following to your `package.json`

```json
"start": "ng serve --live-reload=false",
```
