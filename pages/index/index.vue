<template>
  <view class="container">

    <view class="intro">
      本项目已包含uni ui组件，无需import和注册，可
      直接使用。在代码区键入字母u，即可通过代码助手列
      出所有可用组件。光标置于组件名称处按F1，即可查看组件文档。
    </view>
    <text class="intro">
      详见：
    </text>
    <uni-link :href="href" :text="href"></uni-link>

    <view @click="push">跳转</view>
    <view v-for="(item,index) in arr" :key="index">
      {{index}}
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      href: 'https://uniapp.dcloud.io/component/README?id=uniui',
      arr: [{}]

    }
  },

  async onReachBottom() {
    this.arr.push(...[{}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {},
      {},
      {}, {}, {}, {}

    ])
  },
  async onPullDownRefresh() {
    this.arr.push(...[{}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {}, {},
      {}, {}, {}, {}
    ])

    setTimeout(() => {
      uni.stopPullDownRefresh()
    }, 1000)
  },
  methods: {

    push() {
      uni.navigateTo({
        url: '/pages/detail/index',
        animationType: 'pop-in',
        animationDuration: 200
      })
    }
  }
}
</script>

<style>
  .status_bar {
    height: var(--status-bar-height);
    width: 100%;
  }

  .container {
    padding: 20px;
    font-size: 14px;
    line-height: 24px;
  }
</style>
