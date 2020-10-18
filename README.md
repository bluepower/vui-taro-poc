# vui-taro

[VUI (based on vue3)](https://github.com/bluepower/vui-vc-next) is able to run in cross-platform solutions by [Taro3](https://github.com/NervJS/taro).

- miniprogram (weapp/swan/alipay/tt/qq/jd) - `zh-CN` project
- quickapp - `zh-CN` project
- h5
- react native

### Convert VUI from vui-vc-next to vui-taro

Keep the js and css in SFC, only minor change in the template.

- change tag in template
  - `div` => `view`
  - `img` => `image`
  - `p` => `text`

- change event in template
  - `@click` => `@tap`

> `<style scoped>` is not supported in miniprogram by Taro.

## License

<img src="https://nikoni.top/images/niko-mit.png" alt="MIT License" width="396" height="250"/>
