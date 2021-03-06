---
layout: default
title: faucet-pipeline-sass
---

The configuration is an array of bundles you want to create. Each entry of the
array is an object with two keys: `entryPoint` is the file that should be
compiled, and `target` is the file that should be created (the path is, of
course, modified a little when you use fingerprinting).

To support fingerprinting of images and fonts, use `faucet-pipeline-static` to
fingerprint them. Then you can use the `asset-url` function in your Sass files
to get the correct path. It expects a key from the manifest as its argument, and
outputs an `url()` with the value from the manifest.

If you want to automatically add vendor prefixes to your resulting CSS,
`faucet-pipeline-sass` includes
[`autoprefixer`](https://github.com/postcss/autoprefixer) to do that. It is only
activated if it finds a [`browserslist`](https://github.com/ai/browserslist)
configuration (for example `.browserslistrc`) in your project. It will only add
browser prefixes for the specified browsers.

The resulting configuration might look something like this:

```js
module.exports = {
    sass: [{
        entryPoint: "./example.scss",
        target: "./output/example.css"
    }, {
        entryPoint: "./example2.scss",
        target: "./output/subfolder/example2.css"
    }]
};
```
