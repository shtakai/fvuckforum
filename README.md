# vuckforum

[![GuardRails badge](https://badges.production.guardrails.io/shtakai/fvuckforum.svg)](https://www.guardrails.io)

> fucked up vue

## Configuration for `firebase`

Copy `src/config.sample.js` to `src/config.js`, then update like as followed.

Don't share the confidential information. 🌮

```javascript
const config = {
  apiKey: 'APIKEYFROMFIREBASE',
  authDomain: 'APPNAMEDOMAIN',
  databaseURL: 'DATABASEURL',
  projectId: 'PROJECTID',
  storageBucket: 'STORAGEBUCKED',
  messagingSenderId: 'MESSAGINGSENDERID'
}

export {config}
```


## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
