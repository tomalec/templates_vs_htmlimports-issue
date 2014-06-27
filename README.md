templates_vs_htmlimports-issue
==============================

Polymer, Google Canary, or Juicy/imported-tempalte issue

It appears that when I use custom element that performs dynamic HTML Import (just adds tag to the `<head>`)within another custom element `<my-element>`  which is inside `<template>` with Polymer Binding, `<my-element>`s `.offsetWidth` gets corrupted even if read on `domReady` callback.

It affect Google Canary (native HTML Import support?), under Chrome Stable and IE it works fine.

## [Demo here](https://tomalec.github.io/templates_vs_htmlimports-issue)

Please note, that just on page load (after `domReady`) `<my-element>.offsetWidth == 0`, but as for any other empty `<div>` with `width: 100%` is should be container (`<body>`) size.

It is correct after few milliseconds.