# todo-list-app

> A Vue.js project


## Install nodebrew

``` bash
# install nodebrew
$ curl -L git.io/nodebrew | perl - setup
```

### Set path

```
# set path
$ cd
$ vi .bash_profile
```

```
export PATH=$HOME/.nodebrew/current/bin:$PATH
```

### Reload and Confirm
``` bash
$ source .bash_profile
$ nodebrew
```
## Install node.js, npm and Confirm

``` bash
$ nodebrew install latest
$ nodebrew use latest

# confirm
$ node -v
$ npm -v
```

## Install vue CLI

``` bash
$ npm install -g Vue-cli
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
