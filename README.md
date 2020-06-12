
# 源码分析

## 文件结构

``` bash
/Users/liufang/openSource/FunnyLiu/node-plop
├── LICENSE
├── README.md
├── build-scripts
|  └── clean.js
├── package-lock.json
├── package.json
├── plop-templates
|  └── ava-test.js
├── plopfile.js
├── src
|  ├── actions
|  |  ├── _common-action-add-file.js
|  |  ├── _common-action-interface-check.js
|  |  ├── _common-action-utils.js
|  |  ├── add.js
|  |  ├── addMany.js
|  |  ├── append.js
|  |  ├── index.js
|  |  └── modify.js
|  ├── baked-in-helpers.js
|  ├── fs-promise-proxy.js
|  ├── generator-runner.js
|  ├── index.js
|  ├── node-plop.js
|  └── prompt-bypass.js

directory: 54 file: 132

ignored

```

## 外部模块依赖

请在： http://npm.broofa.com?q=node-plop 查看

## 内部模块依赖

![img](./inner.svg)
  


Node-Plop
======

[![npm](https://img.shields.io/npm/v/node-plop.svg)](https://www.npmjs.com/package/node-plop)
[![CircleCI](https://circleci.com/gh/plopjs/node-plop/tree/master.svg?style=svg)](https://circleci.com/gh/plopjs/node-plop/tree/master)

This is an early publication of the plop core logic being removed from the CLI tool. Main purpose for this is to make it easier for others to automate code generation through processes and tools OTHER than the command line. This also makes it easier to test the code functionality of PLOP without needing to test via the CLI interface.

Once I feel comfortable that this code functions as it should. I'll be driving the plop CLI tool using node-plop.

``` javascript
const nodePlop = require('node-plop');
// load an instance of plop from a plopfile
const plop = nodePlop(`./path/to/plopfile.js`);
// get a generator by name
const basicAdd = plop.getGenerator('basic-add');

// run all the generator actions using the data specified
basicAdd.runActions({name: 'this is a test'}).then(function (results) {
  // do something after the actions have run
});
```
