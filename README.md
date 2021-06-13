# day2
モーダルウィンドウを作ってみる。
[参考](https://reffect.co.jp/vue/understand-component-by-moda-window)

## 学んだこと
- コンポーネント名に注意。HTMLの予約語は使わない[参考](https://qiita.com/fruitriin/items/fe26e3ecb33000a6544e#main%E3%82%B3%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%8D%E3%83%B3%E3%83%88%E3%81%8C%E3%82%A8%E3%83%A9%E3%83%BC%E3%81%AB%E3%81%AA%E3%82%8B)
- イベント修飾子[参考](https://qiita.com/Yorinton/items/f7eb54f05609750da7f5)
  - native: コンポーネントのルート要素のnativeイベントをハンドルする
  - capture: キャプチャモード。DOMツリーで上からたどる[参考](https://qiita.com/hosomichi/items/49500fea5fdf43f59c58)
  - stop: 親子要素でのイベント伝搬を止める
- イベント修飾子を使わずともEmitすればよい
- class-componentの場合、`@Emit('~')`~のところに親で指定しているイベント名を書けば省略してかける
  - 親で指定するイベントもjsに既にあるイベントでなくてもよい。
- eslintの空メソッドに対する警告にはコメントを書けばよい

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Run your unit tests
```
yarn test:unit
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
