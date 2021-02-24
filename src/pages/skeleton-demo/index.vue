<template>
  <view class="v-example">
    <view @tap="showDemo('button')">[ button-demo ]</view>
  </view>
  <view class="v-example">
    <text>Skeleton Content loading</text>
    <button
      @tap="startContentLoading"
    >Test Content loading (delay 2s)</button>
    <v-skeleton
      :class="{'v-example-img': state.contentLoading}"
      v-if="state.showContent"
      title
      title-width="80%"
      :row="7"
      :loading="state.contentLoading"
    >
      <image src="https://nikoni.top/images/others/kongfu.png" class="bg-img" />
    </v-skeleton>
  </view>
  <view class="v-example">
    <text>Skeleton Title placeholders</text>
    <v-skeleton title></v-skeleton>
  </view>
  <view class="v-example">
    <text>Skeleton Avatar placeholders</text>
    <v-skeleton
      title
      avatar
      avatar-size="lg"
    ></v-skeleton>
  </view>
</template>

<script>
import Taro from '@tarojs/taro'
import { reactive } from 'vue'
import VSkeleton from '../../components/skeleton/index.vue'

export default {
  name: 'skeleton-demo',

  inheritAttrs: false,

  components: {
    VSkeleton
  },

  setup() {
    // reactive state
    const state = reactive({
      showContent: false,
      contentLoading: false
    })

    // demo content loading
    const startContentLoading = () => {
      state.showContent = true
      state.contentLoading = true

      setTimeout(() => {
        state.contentLoading = false
      }, 2000)
    }

    const showDemo = (name) => {
      name = name ? name.toLowerCase() : 'button'
      Taro.redirectTo({
        url: `/pages/${name}-demo/index`
      })      
    }

    return {
      state,
      startContentLoading,
      showDemo
    }
  }
}
</script>

<style lang="scss">
@import '../../assets/styles/vui-example.scss';

.bg-img {
  width: 100%;
}

@media (min-width: 401px) {
  .bg-img {
    height: auto;
  }
}
</style>
