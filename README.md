# api documentation for  [gulp-css-spriter (v0.4.0)](https://github.com/MadLittleMods/gulp-css-spriter#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-gulp-css-spriter.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-gulp-css-spriter) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-gulp-css-spriter.svg)](https://travis-ci.org/npmdoc/node-npmdoc-gulp-css-spriter)
#### Sprite Sheet Generation from CSS source files. The best and different approach to sprite sheets.

[![NPM](https://nodei.co/npm/gulp-css-spriter.png?downloads=true)](https://www.npmjs.com/package/gulp-css-spriter)

[![apidoc](https://npmdoc.github.io/node-npmdoc-gulp-css-spriter/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-gulp-css-spriter_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-gulp-css-spriter/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-gulp-css-spriter/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-gulp-css-spriter/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Eric Eastwood",
        "email": "contact@ericeastwood.com",
        "url": "http://ericeastwood.com/"
    },
    "bugs": {
        "url": "https://github.com/MadLittleMods/gulp-css-spriter/issues"
    },
    "dependencies": {
        "bluebird": "^2.9.3",
        "css": "^2.1.0",
        "extend": "^2.0.0",
        "fs-extra": "^0.14.0",
        "gulp-util": "^3.0.1",
        "spritesmith": "^1.0.3",
        "through2": "^0.6.2"
    },
    "description": "Sprite Sheet Generation from CSS source files. The best and different approach to sprite sheets.",
    "devDependencies": {
        "chai": "^1.10.0",
        "chai-as-promised": "^4.1.1",
        "event-stream": "^3.2.2",
        "gulp": "^3.8.10",
        "mocha": "^2.1.0"
    },
    "directories": {},
    "dist": {
        "shasum": "a683107022d66570824be005fefb3231d55d239f",
        "tarball": "https://registry.npmjs.org/gulp-css-spriter/-/gulp-css-spriter-0.4.0.tgz"
    },
    "gitHead": "bff7f92c55337ca937cd8e8ea1e25321aa7842ae",
    "homepage": "https://github.com/MadLittleMods/gulp-css-spriter#readme",
    "keywords": [
        "css",
        "gulp",
        "gulpplugin",
        "gulpfriendly",
        "sprite",
        "spritesheet",
        "sass",
        "less"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "mlm",
            "email": "contact@ericeastwood.com"
        }
    ],
    "name": "gulp-css-spriter",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/MadLittleMods/gulp-css-spriter.git"
    },
    "scripts": {
        "test": "mocha"
    },
    "version": "0.4.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module gulp-css-spriter](#apidoc.module.gulp-css-spriter)
1.  object <span class="apidocSignatureSpan">gulp-css-spriter.</span>spriter_util

#### [module gulp-css-spriter.spriter_util](#apidoc.module.gulp-css-spriter.spriter_util)
1.  [function <span class="apidocSignatureSpan">gulp-css-spriter.spriter_util.</span>matchBackgroundImages (declarationValue, cb)](#apidoc.element.gulp-css-spriter.spriter_util.matchBackgroundImages)
1.  object <span class="apidocSignatureSpan">gulp-css-spriter.spriter_util.</span>backgroundURLRegex



# <a name="apidoc.module.gulp-css-spriter"></a>[module gulp-css-spriter](#apidoc.module.gulp-css-spriter)



# <a name="apidoc.module.gulp-css-spriter.spriter_util"></a>[module gulp-css-spriter.spriter_util](#apidoc.module.gulp-css-spriter.spriter_util)

#### <a name="apidoc.element.gulp-css-spriter.spriter_util.matchBackgroundImages"></a>[function <span class="apidocSignatureSpan">gulp-css-spriter.spriter_util.</span>matchBackgroundImages (declarationValue, cb)](#apidoc.element.gulp-css-spriter.spriter_util.matchBackgroundImages)
- description and source-code
```javascript
function matchBackgroundImages(declarationValue, cb) {
	var backgroundURLMatchAllRegex = new RegExp(backgroundURLRegex.source, "gi");

	return declarationValue.replace(backgroundURLMatchAllRegex, function(match, p1, p2, p3, offset, string) {
		var imagePath = p2;

		return p1 + cb(imagePath) + p3;
	});
}
```
- example usage
```shell
...
			// We find the new images that we found in this chunk verify they exist below
			//		We use an object so we don't get any duplicates
			var newImagesfFromChunkMap = {};
			var backgroundURLMatchAllRegex = new RegExp(spriterUtil.backgroundURLRegex.source, "gi");
			chunkBackgroundImageDeclarations.forEach(function(declaration) {

				// Match each background image in the declaration (there could be multiple background images per value)
				spriterUtil.matchBackgroundImages(declaration.value, function(imagePath) {
					imagePath = path.join(path.dirname(chunk.path), imagePath);

					// If not already in the overall list of images collected
					// Add to the queue/list of images to be verified
					if(!imageMap[imagePath]) {
						newImagesfFromChunkMap[imagePath] = true;
					}
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
