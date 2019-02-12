

<div align="center">
    <img src="docs/readme-logo.png">
    <h1>cypress-plugin-retries</h1>
    <a href="https://www.npmjs.com/package/cypress-plugin-retries"><img src="https://img.shields.io/npm/v/cypress-plugin-retries.svg?style=flat"></a>
    <a href="https://www.npmjs.com/package/cypress-plugin-retries"><img src="https://img.shields.io/npm/dt/cypress-plugin-retries.svg"></a>
    <a href="https://github.com/bkucera/cypress-plugin-retries/blob/master/LICENSE"><img src="https://img.shields.io/github/license/bkucera/cypress-plugin-retries.svg"></a>

<p>A Cypress plugin to retry failed tests</p>

</div>

> **Please report bugs in the issues of this repo.**

> [Please refer to this issue for updates about official cypress retry support](https://github.com/cypress-io/cypress/issues/1313)

![](docs/readme-screenshot.png)
![](2019-02-12-13-29-53.png)

### Installation

Add the plugin to `devDependencies`
```bash
npm install -D cypress-plugin-retries
```

At the top of **`cypress/support/index.js`**:
```js
require('cypress-plugin-retries')
```


### Usage

Use the environment variable `CYPRESS_RETRIES` to set the retry number:
```bash
CYPRESS_RETRIES=2 npm run cypress
```
**or** Use `Cypress.env('RETRIES')` in your spec file:
```js
Cypress.env('RETRIES', 2)
```
**or** Use `mocha`'s `this.retries(n)` inside of a test:
> Note: **must use `function()` notation, not arrows `()=>{}`**
```js
it('test', function() {
    this.retries(2)
})
```

### License
[MIT](LICENSE)
