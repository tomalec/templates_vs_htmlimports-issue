templates_vs_htmlimports-issue
==============================

Issues:
 - [Chromium#389566](https://code.google.com/p/chromium/issues/detail?id=389566),
 - [Polymer#554](https://github.com/Polymer/polymer/issues/554),
 - [Polyjuice/Launcher#82](https://github.com/Polyjuice/Launcher/issues/82)

It appears that when I use custom element that performs dynamic HTML Import (just adds tag to the `<head>`)within another custom element `<my-element>`  which is inside `<template>` with Polymer Binding, `<my-element>`s `.offsetWidth` gets corrupted even if read on `domReady` callback.

It affect Google Canary (native HTML Import support?), under Chrome Stable and IE it works fine.

## [Demo here](https://tomalec.github.io/templates_vs_htmlimports-issue)

Please note, that just on page load (after `domReady`) `<my-element>.offsetWidth == 0`, but as for any other empty `<div>` with `width: 100%` is should be container (`<body>`) size.

It is correct after few milliseconds.

### Temporary workaround is in [separated branch](https://github.com/tomalec/templates_vs_htmlimports-issue/tree/workaround)
[Remove dynamic import from attaching flow](https://github.com/tomalec/templates_vs_htmlimports-issue/blob/workaround/components/dynamic-import.html#L19)