# api documentation for  [react-tap-event-plugin (v2.0.1)](http://facebook.github.io/react)  [![npm package](https://img.shields.io/npm/v/npmdoc-react-tap-event-plugin.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-react-tap-event-plugin) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-react-tap-event-plugin.svg)](https://travis-ci.org/npmdoc/node-npmdoc-react-tap-event-plugin)
#### Facebook's TapEventPlugin, temporarily available on npm until its made public in their repo

[![NPM](https://nodei.co/npm/react-tap-event-plugin.png?downloads=true)](https://www.npmjs.com/package/react-tap-event-plugin)

[![apidoc](https://npmdoc.github.io/node-npmdoc-react-tap-event-plugin/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-react-tap-event-plugin_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-react-tap-event-plugin/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-react-tap-event-plugin/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-react-tap-event-plugin/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "bugs": {
        "url": "https://github.com/zilverline/react-tap-event-plugin/issues"
    },
    "dependencies": {
        "fbjs": "^0.8.6"
    },
    "description": "Facebook's TapEventPlugin, temporarily available on npm until its made public in their repo",
    "devDependencies": {},
    "directories": {},
    "dist": {
        "shasum": "316beb3bc6556e29ec869a7293e89c826a9074d2",
        "tarball": "https://registry.npmjs.org/react-tap-event-plugin/-/react-tap-event-plugin-2.0.1.tgz"
    },
    "files": [
        "src/"
    ],
    "gitHead": "08fc674679ed52cf135a2f8b43760db39d7ae885",
    "homepage": "http://facebook.github.io/react",
    "keywords": [
        "TapEventPlugin",
        "react",
        "touch",
        "delay",
        "300ms",
        "react-tap-event-plugin"
    ],
    "licenses": [
        {
            "type": "Apache-2.0",
            "url": "http://www.apache.org/licenses/LICENSE-2.0"
        }
    ],
    "main": "src/injectTapEventPlugin.js",
    "maintainers": [
        {
            "name": "s0meone",
            "email": "daniel@danielvanhoesel.nl"
        }
    ],
    "name": "react-tap-event-plugin",
    "optionalDependencies": {},
    "peerDependencies": {
        "react": "^15.4.0-0",
        "react-dom": "^15.4.0-0"
    },
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/zilverline/react-tap-event-plugin.git"
    },
    "scripts": {
        "test": "echo \"Error: no test specified\" && exit 1"
    },
    "version": "2.0.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module react-tap-event-plugin](#apidoc.module.react-tap-event-plugin)
1.  object <span class="apidocSignatureSpan">react-tap-event-plugin.</span>TouchEventUtils

#### [module react-tap-event-plugin.TouchEventUtils](#apidoc.module.react-tap-event-plugin.TouchEventUtils)
1.  [function <span class="apidocSignatureSpan">react-tap-event-plugin.TouchEventUtils.</span>extractSingleTouch (nativeEvent)](#apidoc.element.react-tap-event-plugin.TouchEventUtils.extractSingleTouch)



# <a name="apidoc.module.react-tap-event-plugin"></a>[module react-tap-event-plugin](#apidoc.module.react-tap-event-plugin)



# <a name="apidoc.module.react-tap-event-plugin.TouchEventUtils"></a>[module react-tap-event-plugin.TouchEventUtils](#apidoc.module.react-tap-event-plugin.TouchEventUtils)

#### <a name="apidoc.element.react-tap-event-plugin.TouchEventUtils.extractSingleTouch"></a>[function <span class="apidocSignatureSpan">react-tap-event-plugin.TouchEventUtils.</span>extractSingleTouch (nativeEvent)](#apidoc.element.react-tap-event-plugin.TouchEventUtils.extractSingleTouch)
- description and source-code
```javascript
extractSingleTouch = function (nativeEvent) {
  var touches = nativeEvent.touches;
  var changedTouches = nativeEvent.changedTouches;
  var hasTouches = touches && touches.length > 0;
  var hasChangedTouches = changedTouches && changedTouches.length > 0;

  return !hasTouches && hasChangedTouches ? changedTouches[0] :
         hasTouches ? touches[0] :
         nativeEvent;
}
```
- example usage
```shell
...

var Axis = {
  x: {page: 'pageX', client: 'clientX', envScroll: 'currentPageScrollLeft'},
  y: {page: 'pageY', client: 'clientY', envScroll: 'currentPageScrollTop'}
};

function getAxisCoordOfEvent(axis, nativeEvent) {
  var singleTouch = TouchEventUtils.extractSingleTouch(nativeEvent);
  if (singleTouch) {
    return singleTouch[axis.page];
  }
  return axis.page in nativeEvent ?
    nativeEvent[axis.page] :
    nativeEvent[axis.client] + ViewportMetrics[axis.envScroll];
}
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
