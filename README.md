# npmtest-react-day-picker

#### basic test coverage for  [react-day-picker (v5.2.3)](https://react-day-picker.js.org)  [![npm package](https://img.shields.io/npm/v/npmtest-react-day-picker.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-react-day-picker) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-react-day-picker.svg)](https://travis-ci.org/npmtest/node-npmtest-react-day-picker)

#### Flexible date picker component for React

[![NPM](https://nodei.co/npm/react-day-picker.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/react-day-picker)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-react-day-picker/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-react-day-picker/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-react-day-picker/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-react-day-picker/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-react-day-picker/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-react-day-picker/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-react-day-picker/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-react-day-picker/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-react-day-picker/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-react-day-picker/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-react-day-picker/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-react-day-picker/build/test-report.html](https://npmtest.github.io/node-npmtest-react-day-picker/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-react-day-picker/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-react-day-picker/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-react-day-picker/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-react-day-picker/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-react-day-picker/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-react-day-picker/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-react-day-picker/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-react-day-picker/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "react-day-picker",
    "version": "5.2.3",
    "description": "Flexible date picker component for React",
    "main": "DayPicker.js",
    "style": "lib/style.css",
    "files": [
        "DayPicker.js",
        "lib",
        "moment.js",
        "utils.js"
    ],
    "directories": {
        "doc": "docs"
    },
    "scripts": {
        "clean": "rimraf coverage lib",
        "lint": "eslint src test",
        "prettify": "prettier --write --single-quote --trailing-comma=\"es5\" \"{src,test,examples/src}/**/*.js\"",
        "precommit": "lint-staged",
        "test": "mocha --compilers js:babel-core/register --require ./test/setup.js --recursive --reporter spec",
        "test:watch": "npm test -- --watch",
        "test:files": "mocha --compilers js:babel-core/register --require ./test/setup.js --reporter spec --bail --watch",
        "cover": "babel-node ./node_modules/istanbul/lib/cli cover -- _mocha --recursive --reporter spec",
        "check": "npm run lint && npm run test",
        "prerelease": "npm run check && npm run build",
        "build": "npm run build:node && npm run build:production && npm run build:development",
        "build:node": "babel ./src -d ./lib/src --source-maps && npm run build:css",
        "build:development": "NODE_ENV=development webpack",
        "build:production": "NODE_ENV=production webpack -p",
        "build:css": "postcss src/style.css --use autoprefixer -d lib/ --no-map",
        "examples:clean": "rimraf examples/built",
        "examples:build": "npm run examples:clean && cd examples && npm run build && cd ..",
        "docs:clean": "rimraf _book",
        "docs:prepare": "gitbook install",
        "docs:build": "npm run docs:prepare && gitbook build",
        "docs:serve": "gitbook serve",
        "docs:publish": "npm run docs:clean && npm run docs:build && npm run examples:build && rimraf _book/examples && mv examples/built _book/examples && cd _book && ECHO react-day-picker.js.org > CNAME && git init && git commit --allow-empty -m 'Update docs and examples' && git checkout -b gh-pages && touch .nojekyll && git add . && git commit -am 'Update docs and examples' && git push git@github.com:gpbl/react-day-picker gh-pages --force"
    },
    "repository": {
        "type": "git",
        "url": "https://github.com/gpbl/react-day-picker.git"
    },
    "keywords": [
        "react",
        "react-component",
        "component",
        "calendar",
        "date-picker",
        "datepicker",
        "date",
        "picker",
        "moment",
        "momentjs"
    ],
    "author": "Giampaolo Bellavite <io@gpbl.org>",
    "license": "MIT",
    "bugs": {
        "url": "https://github.com/gpbl/react-day-picker/issues"
    },
    "homepage": "https://react-day-picker.js.org",
    "peerDependencies": {
        "react": "~0.13.x || ~0.14.x || ^15.0.0"
    },
    "devDependencies": {
        "autoprefixer": "6.7.7",
        "babel-cli": "6.24.1",
        "babel-core": "6.24.1",
        "babel-eslint": "7.2.2",
        "babel-loader": "6.4.1",
        "babel-preset-es2015": "6.24.1",
        "babel-preset-react": "6.24.1",
        "babel-preset-stage-1": "6.24.1",
        "chai": "3.5.0",
        "chai-enzyme": "0.6.1",
        "cheerio": "0.22.0",
        "coveralls": "2.13.0",
        "enzyme": "2.8.2",
        "eslint": "3.19.0",
        "eslint-config-airbnb": "14.1.0",
        "eslint-config-prettier": "1.6.0",
        "eslint-plugin-import": "2.2.0",
        "eslint-plugin-jsx-a11y": "4.0.0",
        "eslint-plugin-react": "6.10.3",
        "gitbook-cli": "2.3.0",
        "husky": "0.13.3",
        "istanbul": "1.1.0-alpha.1",
        "jsdom": "9.0.0",
        "lint-staged": "3.4.0",
        "mocha": "3.2.0",
        "moment": "2.18.1",
        "postcss-cli": "3.1.1",
        "prettier": "1.1.0",
        "react": "15.5.4",
        "react-addons-test-utils": "15.5.1",
        "react-dom": "15.5.4",
        "react-hot-loader": "3.0.0-beta.6",
        "react-test-renderer": "15.5.4",
        "rimraf": "2.6.1",
        "sinon": "2.1.0",
        "sinon-chai": "2.9.0",
        "webpack": "2.4.0"
    },
    "dependencies": {
        "prop-types": "^15.5.8"
    },
    "precommit": "lint-staged",
    "lint-staged": {
        "*.js": [
            "npm run prettify",
            "git add"
        ]
    },
    "bin": {}
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
