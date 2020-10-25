<template>
  <image
    src="https://nikoni.top/images/others/cg.jpg"
    class="bg-img"
  />
  <v-cool-button
    :scale="0.8"
    class="btn-lt"
  />
  <v-cool-button
    :scale="0.8"
    class="btn-rt"
  />
  <view class="v-example">
    <v-one-piece :scale="1.2" />
  </view>
  <view class="v-example">
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

.bg-img {
  width: 100vw;
}

.btn-lt {
  position: absolute;
  top: 200px;
  left: 200px;
}

.btn-rt {
  position: absolute;
  top: 200px;
  left: 350px;
}

@media (min-width: 640px) {
  .bg-img {
    width: 720px;
    height: 540px;
  }
}
</style>
