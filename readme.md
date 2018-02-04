# wepy-sticker 小程序表情包组件

## Install 安装

```
$ npm i wepy-sticker -S
```

## Usage 使用

```html
// index.wpy

<style lang="less">
  .page-container {
    width: 750rpx;
    height: 400rpx;
    border: 1px solid rgba(0,0,0,.3);
    box-sizing: border-box;
  }

  .input {
    width: 750rpx;
    border: 1px solid #000;
  }
</style>

<template>
  <view>
    <input class="input" value="{{inputValue}}"/>
  </view>
  <view class="page-container">
    <sticker :config.sync="stickerConfig"></sticker>
  </view>
</template>

<script>
  import wepy from 'wepy'
  import Sticker from 'wepy-sticker'
  import stickerDefaultConfig from 'wepy-sticker/defaultConfig'

  export default class Index extends wepy.page {
    data = {
      stickerConfig: stickerDefaultConfig,
      inputValue: ''
    }

    components = {
      sticker: Sticker
    }

    events = {
      'wepy-sticker-tap': (stickerObj) => {
        console.log(stickerObj)
        this.inputValue += stickerObj.wrappedKey
      }
    }
  }
</script>

```

## Events 事件

```js

events = {
    'wepy-sticker-tap': (stickerObj) => {

    }
}

```

## License

MIT