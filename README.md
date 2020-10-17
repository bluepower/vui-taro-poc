# vui-taro

VUI (based on vue3) is able to run in cross-platform solutions by [Taro3](https://github.com/NervJS/taro).

- miniprogram (weapp/swan/alipay/tt/qq/jd) - `zh-CN` project
- quickapp - `zh-CN` project
- h5
- react native

### Convert VUI from vui-vc-next to vui-taro

- change tag in template
  - `div` => `view`
  - `img` => `image`

- change event in template
  - `@click` => `@tap`

> `<style scoped>` is not supported in miniprogram by Taro.
