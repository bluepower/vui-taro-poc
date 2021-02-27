<template>
  <image
    src="https://nikoni.top/images/others/cg.jpg"
    class="bg-img"
  />
  <v-cool-button
    :scale="0.5"
    class="btn-lt"
  />
  <v-cool-button
    :scale="0.5"
    class="btn-rt"
  />
  <view class="v-example">
    <v-one-piece :scale="1.2" />
  </view>
  <view class="v-example v-example-nav">
    <view @tap="showDemo('skeleton')">[ skeleton-demo ]</view>
  </view>  
</template>

<script>
import Taro from '@tarojs/taro'
import VCoolButton from '../../components/misc/cool-button/index.vue'
import VOnePiece from '../../components/misc/op/index.vue'

export default {
  name: 'button-demo',

  components: {
    [VCoolButton.name]: VCoolButton,
    [VOnePiece.name]: VOnePiece
  },

  setup() {
    const showDemo = (name) => {
      name = name ? name.toLowerCase() : 'button'
      Taro.redirectTo({
        url: `/pages/${name}-demo/index`
      })      
    }

    return {
      showDemo
    }
  }
}
</script>

<style lang="scss">
@import '../../assets/styles/vui-example.scss';

.v-example-nav {
  margin-top: 80px;
}

.bg-img {
  width: 100vw;
}

.btn-lt {
  position: absolute;
  top: 140px;
  left: 120px;
}

.btn-rt {
  position: absolute;
  top: 140px;
  left: 290px;
}

@media (min-width: 640px) {
  .bg-img {
    width: 720px;
    height: 540px;
  }
}
</style>
