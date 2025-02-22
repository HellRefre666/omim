# MAPS.ME

[MAPS.ME](https://maps.me) is an open source cross-platform offline maps application,
built on top of crowd-sourced OpenStreetMap data. It was publicly released
for [iOS](https://itunes.apple.com/app/id510623322) and
[Android](https://play.google.com/store/apps/details?id=com.mapswithme.maps.pro).

![](docs/screenshots.jpg)

## Submodules

This repository contains submodules. Clone it with `git clone --recursive`. If you forgot,
run `git submodule update --init --recursive`.

## Translations

If you want to improve app translations or add more search synonyms, please check our [wiki](https://github.com/mapsme/omim/wiki).

## Compilation

To compile the project, you would need to initialize private key files. Run
`configure.sh` and press Enter to create empty files, good enough to build desktop
and Android debug packages.

For detailed installation instructions and Android/iOS building process,
see [INSTALL.md](https://github.com/mapsme/omim/tree/master/docs/INSTALL.md).

## Building maps

To create one or many map files, first build the project, then use python module [maps_generator](https://github.com/mapsme/omim/tree/master/tools/python/maps_generator).

## Map styles

MAPS.ME uses its own binary format for map styles, `drules_proto.bin`, which is compiled from
[MapCSS](https://wiki.openstreetmap.org/wiki/MapCSS) using modified Kothic library.
Feature set in MWM files depends on a compiled style, so make sure to rebuild maps after
releasing a style.

For development, use MAPS.ME Designer app along with its generator tool: these allow
for quick rebuilding of a style and symbols, and for producing a zoom-independent
feature set in MWM files.

See [STYLES.md](https://github.com/mapsme/omim/tree/master/docs/STYLES.md) for the
format description, instructions on building a style and some links.

## Development

You would need Qt 5 for development, most other libraries are included into the
repository: see `3party` directory. The team uses mostly XCode and Qt Creator,
though these are not mandatory. We have an established
[c++ coding style](https://github.com/mapsme/omim/blob/master/docs/CPP_STYLE.md) and [Objective-C coding style](https://github.com/mapsme/omim/blob/master/docs/OBJC_STYLE.md).

**You can turn on experimental public transport support.** For details please read [simple instruction.](https://github.com/mapsme/omim/blob/master/docs/EXPERIMENTAL_PUBLIC_TRANSPORT_SUPPORT.md)

See [CONTRIBUTING.md](https://github.com/mapsme/omim/blob/master/docs/CONTRIBUTING.md)
for the repository initialization process, the description of all the directories
of this repository and other development-related information.

All contributors must sign a [Contributor Agreement](https://github.com/mapsme/omim/blob/master/docs/CLA.md),
so both our and their rights are protected.

## Feedback

Please report bugs and suggestions to [the issue tracker](https://github.com/mapsme/omim/issues),
or by mail to bugs@maps.me.

## Authors and License

This source code is Copyright (C) 2020 My.com B.V. (Mail.Ru Group), published under Apache Public License 2.0,
except third-party libraries. See [NOTICE](https://github.com/mapsme/omim/blob/master/NOTICE)
and English | [简体中文](./README_CN.md)

vConsole
===

A lightweight, extendable front-end developer tool for mobile web page.

vConsole is framework-free, you can use it in Vue or React or any other framework application.

Now vConsole is the official debugging tool for WeChat Miniprograms.

---

## Features

- Logs: `console.log|info|error|...`
- Network: `XMLHttpRequest`, `Fetch`, `sendBeacon`
- Element: HTML elements tree
- Storage: `Cookies`, `LocalStorage`, `SessionStorage`
- Execute JS command manually
- Custom plugins

For details, please see the screenshots below.

---

## Release Notes

Latest version: [![npm version](https://img.shields.io/npm/v/vconsole/latest.svg)](https://www.npmjs.com/package/vconsole)

Detailed release notes for each version are available on [Changelog](./CHANGELOG.md).

---

## Guide

See [Tutorial](./doc/tutorial.md) for more usage details.

For installation, there are 2 primary ways of adding vConsole to a project:

#### Method 1: Using npm (Recommended)

```bash
$ npm install vconsole
```

```javascript
import VConsole from 'vconsole';

const vConsole = new VConsole();
// or init with options
const vConsole = new VConsole({ theme: 'dark' });

// call `console` methods as usual
console.log('Hello world');

// remove it when you finish debugging
vConsole.destroy();
```

#### Method 2: Using CDN in HTML:

```html
<script src="https://unpkg.com/vconsole@latest/dist/vconsole.min.js"></script>
<script>
  // VConsole will be exported to `window.VConsole` by default.
  var vConsole = new window.VConsole();
</script>
```

Available CDN:

- https://unpkg.com/vconsole@latest/dist/vconsole.min.js
- https://cdn.jsdelivr.net/npm/vconsole@latest/dist/vconsole.min.js

---

## Preview

[http://wechatfe.github.io/vconsole/demo.html](http://wechatfe.github.io/vconsole/demo.html)

![](./doc/screenshot/qrcode.png)

---

## Screenshots

### Overview

<details>
  <summary>Light theme</summary>

![](./doc/screenshot/overview_light.jpg)
</details>

<details>
  <summary>Dark theme</summary>

![](./doc/screenshot/overview_dark.jpg)
</details>

### Log Panel

<details>
  <summary>Log styling</summary>

![](./doc/screenshot/plugin_log_types.jpg)
</details>

<details>
  <summary>Command line</summary>

![](./doc/screenshot/plugin_log_command.jpg)
</details>

### System Panel

<details>
  <summary>Performance info</summary>

![](./doc/screenshot/plugin_system.jpg)
</details>

<details>
  <summary>Output logs to different panel</summary>

```javascript
console.log('output to Log panel.')
console.log('[system]', 'output to System panel.')
```
</details>

### Network Panel

<details>
  <summary>Request details</summary>

![](./doc/screenshot/plugin_network.jpg)
</details>

### Element Panel

<details>
  <summary>Realtime HTML elements structure</summary>

![](./doc/screenshot/plugin_element.jpg)
</details>

### Storage Panel

<details>
  <summary>Add, edit, delete or copy Cookies / LocalStorage / SessionStorage</summary>

![](./doc/screenshot/plugin_storage.jpg)
</details>

---

## Documentation

vConsole:

 - [Tutorial](./doc/tutorial.md)
 - [Public Properties & Methods](./doc/public_properties_methods.md)
 - [Builtin Plugin: Properties & Methods](./doc/plugin_properties_methods.md)

Custom Plugin:

 - [Plugin: Getting Started](./doc/plugin_getting_started.md)
 - [Plugin: Building a Plugin](./doc/plugin_building_a_plugin.md)
 - [Plugin: Event List](./doc/plugin_event_list.md)

---

## Third-party Plugins

 - [vConsole-sources](https://github.com/WechatFE/vConsole-sources)
 - [vconsole-webpack-plugin](https://github.com/diamont1001/vconsole-webpack-plugin)
 - [vconsole-stats-plugin](https://github.com/smackgg/vConsole-Stats)
 - [vconsole-vue-devtools-plugin](https://github.com/Zippowxk/vue-vconsole-devtools)
 - [vconsole-outputlog-plugin](https://github.com/sunlanda/vconsole-outputlog-plugin)
 - [vite-plugin-vconsole](https://github.com/vadxq/vite-plugin-vconsole)

---

## Feedback

QQ Group: 497430533

![](./doc/screenshot/qq_group.png)

---

## License

[The MIT License](./LICENSE)
) files for more information.
