# Weex Ui

[![Build Status](https://img.shields.io/travis/alibaba/weex-ui.svg?style=flat-square)](https://travis-ci.org/alibaba/weex-ui)
[![GitHub last commit](https://img.shields.io/github/last-commit/alibaba/weex-ui.svg?style=flat-square)](https://github.com/alibaba/weex-ui/commits/dev)
[![npm](https://img.shields.io/npm/v/weex-ui.svg?maxAge=3600&style=flat-square)](https://www.npmjs.com/package/weex-ui)
[![NPM downloads](https://img.shields.io/npm/dm/weex-ui.svg?style=flat-square)](https://npmjs.org/package/weex-ui)
[![NPM all downloads](https://img.shields.io/npm/dt/weex-ui.svg?style=flat-square)](https://npmjs.org/package/weex-ui)
[![GitHub closed issues](https://img.shields.io/github/issues-closed/alibaba/weex-ui.svg?style=flat-square)](https://github.com/alibaba/weex-ui/issues?utf8=%E2%9C%93&q=)
![Accessibility](https://img.shields.io/badge/accessibility-support-orange.svg?style=flat-square)
[![Join the chat at https://gitter.im/alibaba-weex-ui/chat](https://img.shields.io/gitter/room/alibaba/weex-ui.svg?style=flat-square)](https://gitter.im/alibaba-weex-ui/chat?utm_source=share-link&utm_medium=link&utm_campaign=share-link)


> A rich interaction, lightweight, high performance UI library based on [Weex](https://github.com/apache/incubator-weex).

## Docs
- [**English**](https://alibaba.github.io/weex-ui/#/)
- [中文文档](https://alibaba.github.io/weex-ui/#/cn/)
- [Weex + Ui - Weex Conf 2018](https://alibaba.github.io/weex-ui/#/docs/weex-ui-weex-conf-2018)

## Demo
<img src="https://img.alicdn.com/tfs/TB1O2ulhgoQMeJjy0FoXXcShVXa-1282-986.jpg" width=540/>

*Try [it](https://h5.m.taobao.com/trip/weex-ui/index.html?_wx_tpl=https%3A%2F%2Fh5.m.taobao.com%2Ftrip%2Fweex-ui%2Fdemo%2Findex.native-min.js) with [Fliggy](http://www.fliggy.com/mobile/?spm=181.52816.a1z6c.19.1fcc529aNQO84O&ad_id=&am_id=1301048151a679d80b29)、[Taobao](https://mpage.taobao.com/hd/download.html?spm=a21bo.50862.201858.1.5523e29eOKuPPN)、[Tmall](https://pages.tmall.com/wow/portal/act/app-download?spm=875.7931836/B.a2226mz.16&scm=1027.1.1.1)、[Weex Playground](https://weex.apache.org/cn/playground.html) or any browsers now!*    &nbsp;&nbsp;[简体中文>>](./README_cn.md)


## Installation

```shell
npm i weex-ui -S
```

## Usage
  
```html
<template>
  <div>
    <wxc-button text="Open Popup"
                @wxcButtonClicked="buttonClicked">
    </wxc-button>
    <wxc-popup width="500"
               pos="left"
               :show="isShow"
               @wxcPopupOverlayClicked="overlayClicked">
    </wxc-popup>
  </div>
</template>

<script>
  import { WxcButton, WxcPopup } from 'weex-ui';
  // or
  // import WxcButton from 'weex-ui/packages/wxc-button';
  // import WxcPopup from 'weex-ui/packages/wxc-popup';
  module.exports = {
    components: { WxcButton, WxcPopup },
    data: () => ({
      isShow: false
    }),
    methods: {
      buttonClicked () {
        this.isShow = true;
      },
      overlayClicked () {
        this.isShow = false;
      }
    }
  };
</script>
```

#### Before use

In order not to pack all the components, you need use [babel-plugin-component](https://www.npmjs.com/package/babel-plugin-component) import specified component.  At the same time, if you do not install babel-preset-stage-0, you also need to install it.

```shell
npm i babel-preset-stage-0 babel-plugin-component  -D
```

```json
{
  "presets": ["es2015", "stage-0"],
  "plugins": [
    [
      "component",
      {
        "libraryName": "weex-ui",
        "libDir": "packages",
         "style": false
      }
    ]
  ]
}
```

#### More
- More details can be found in [**How to use with weex-toolkit**](/docs/with-weex-toolkit.md) and [weex-ui-demo](https://github.com/tw93/weex-ui-demo).
- If `webpack.config.js`  babel-loader has a exclude for node_modules, Please turn on for week-ui `exclude: /node_modules(?!(\/|\\).*(weex).*)/`.
- You can find more examples [here](https://github.com/alibaba/weex-ui/tree/master/example). Write once and support iOS / Android / Html5 right now!
- If you have a problem, you can get help by looking for [FAQ](https://alibaba.github.io/weex-ui/#/faq) and [issue list](https://github.com/alibaba/weex-ui/issues?utf8=%E2%9C%93&q=).
- In order to get the latest features and better experience, please focus on the [ChangeLog](https://github.com/alibaba/weex-ui/releases) and **often update `weex-ui` to the latest**.

## Development

```shell
npm i
npm run start
```

Once it has been compiled, a browser window will be opened automatically. You can switch to developer mode to see the demo. And there will be a QR code that you can use to try the demo on your phone in the console.

## Support

- Use it with NPM.
- **Star it** if you like.
- If you have any ideas or suggestions to improve Weex Ui, welcome to submit a [PR](./CONTRIBUTING.md).
- Having a problem getting something to work or want to know why we setup something in a certain way? [File a GitHub Issue](https://github.com/alibaba/weex-ui/issues/new).
- <details>
    <summary>Join our chat at dingtalk.</summary>
    <img alt="Join the chat at dingtalk" src="https://img.alicdn.com/tfs/TB1DSvMg2DH8KJjy1XcXXcpdXXa-750-850.jpg" width="240"/>
  </details>

## License
- The [MIT License](http://opensource.org/licenses/MIT)
- Please feel free to use and contribute to the development.
