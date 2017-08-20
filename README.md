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

Adding another file named, for example, `another.js` to src and running the same command:

```
$ babel src --presets es2015 -d build
```

results in the two files being generated.

```
src/another.js -> build/another.js
src/main.js -> build/main.js
```

You can also combine the two files in src into one bundle file using the following:

```
$ babel src --presets es2015 -o build/bundle.js
```

To generate source maps also indicate the `-s` argument:

```
babel src --presets es2015 -o build/bundle.js -s
```

This will output:

```
buid/bundle.js
buid/bundle.js.map
```

Another useful argument is the `-w` which watches for file changes in the `src` directory:


```
babel src --presets es2015 -o build/bundle.js -s -w
```

### Using a `.babelrc` file


Create a `.babelrc` file to easily configure the babel command

```
// .babelrc
{
    "presets": [ "es2015" ],
    "sourceMaps": true
}
```

You can also configure specific plugins in the config

```
// .babelrc
{
    "plugins": ["transform-es2015-arrow-functions"],
    "presets": [ "es2015" ],
    "sourceMaps": true
}
```

Given the above file the command can be shortened to:

```
babel src -o build/bundle.js
```





