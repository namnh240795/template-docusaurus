---
title: Icons
sidebar_position: 3
---

# Generate Icons

[Full Example](https://github.com/namnh240795/react-native-svgs-to-icon-example)

Use custom iconfont with package `react-native-svgs-to-icon`

- Installation packages as devDependencies

```bash
  yarn add -D patch-package webpack-iconfont-plugin-nodejs react-native-asset react-native-svgs-to-icon
```

- configs `react-native.config.js`

```js
module.exports = {
  'react-native-svgs-to-icon': {
    output: './src/components', // icon components output destination
    input: './svgs', // svgs folder input destination
    fontOutput: './fontOutput', // font output destination could put this folder into .gitingore
    fontName: 'MyFont', // font name
    fontOutputCopyTo: './src/assets/fonts', // copy font to assets/fonts
  },
  assets: ['./src/assets/fonts'],
};
```

- configs post install in `package.json`

```js
{
  scripts: {
    "postinstall": "react-native-svgs-to-icon init && patch-package && react-native-svgs-to-icon generate && react-native-asset"
  }
}
```

- run `yarn`

- rebuild app

- usage:

```ts
export default function App() {
  return (
    <Icon name='keyboard_double_arrow_up' style={{ marginTop: 100 }} size={24} color='green' />
  );
}
```
