# babel-learning

Learning Babel

## Babel Packages

```
babel-core
babel-cli
babel-plugin-*

babel-preset-*
```

## Install

### Global Install

```
npm install -g babel-cli
```

Confirm install

```
npm ls -g --depth 0
```

Sample output

```
/home/ubuntu/.nvm/versions/node/v4.7.3/lib
├── babel-cli@6.24.1
└── npm@2.15.11
```

### Local Install

```
npm init -y
npm install babel-cli --save-dev
babel --version # global
node_modules/.bin/babel --version #local
```

## Global 

Sample output

```
$ babel src --presets es2015
"use strict";

var greeting = "Hi";
console.log("-- " + greeting + " Craig");
```

Sample build

```
$ babel src --presets es2015 --out-dir build
src/main.js -> build/main.js
```

```
$ babel src --presets es2015 -d build
src/main.js -> build/main.js
```


