---
layout: default
title: CLI
---

If you call the `faucet` command without any arguments, it will default to
building your project according to the configuration in the file
`faucet.config.js` in the current directory. You have the following options:

* `-c $FILENAME` or `--config=$FILENAME`: Use the file `$FILENAME` as the
  configuration file.
* `-w` or `--watch`: Build once, afterward watch for file changes and rebuild
  when a file that is used for one of your bundles changes. See [file
  watching](/watching) for details.
* `--no-fingerprint`: Suppress fingerprinting in the file names. See
[fingerprinting & manifest](/manifest) for details.
* `--compact`: Use a compact output format for all pipelines that support it
  (currently `faucet-pipeline-sass` and `faucet-pipeline-js`). Comments will be
  stripped from the output etc. This doesn't do minification (variable name
  mangling etc.) due to our `view-source:` conviction.

We recommend that you use a combination of `--watch` and `--no-fingerprint` for
development (fingerprinting is not very useful in development and it also
reduces clutter on your disk) and `--compact` for production.
