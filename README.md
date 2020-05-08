# todo-list-app

> A Vue.js project

# How to setup environment

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

## Install yarn and Confirm

``` bash
$ npm install -g yarn

# confirm
$ yarn -v
```

## Install vue CLI

``` bash
$ yarn global add @vue/cli
# or
$ npm install -g Vue-cli
```

## Build Setup

``` bash
# install dependencies
$ yarn install
# or
$ npm install

# serve with hot reload at localhost:8080
$ yarn run serve
# or
$ npm run serve

# build for production with minification
$ yarn run build
# or
$ npm run build

# build for production and view the bundle analyzer report
$ yarn run build --report
# or
$ npm run build --report
```
For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

# How to start project

## 1. Clone this repository

``` bash
$ git clone git@github.com:smd101/todo-list-app.git
```

## 2. Install all the dependencies
Install all the dependencies listed in package.json in node_modules.
``` bash
$ yarn install
```

## 3. Run serve
execute vue-cli-service serve.
``` bash
$ yarn run serve

# You will see a message similar to the following.
DONE  Compiled successfully in 5294ms                                                                                         

  App running at:
  - Local:   http://localhost:8080/
  - Network: http://172.31.1.1:8080/

  Note that the development build is not optimized.
  To create a production build, run yarn build.
  
# Try access 'http://localhost:8080/'!!
```
