<template>
  <div class="none-page">
    <img class="image" :src="noneImgUrl" alt="">
    <slot name="title"></slot>
    <slot name="button"></slot>
  </div>
</template>

<script>
export default {
  name: "none",
  data(){
    return {
      noneImgUrl:"https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/default%402x.png",


    }
  },
  computed:{

  },
  created() {

  },
  methods:{

  }
}
</script>

<style scoped lang="scss">
.none-page{
  text-align: center;
  .image{
    width: 50%;
    margin-top: 200rpx;
    margin-bottom: 50rpx;
  }

  .title{
    font-size: 36rpx;
    line-height: 50rpx;
  }

  .desc{
    margin: 5rpx auto 48rpx auto;
    font-size: 24rpx;
    line-height: 34rpx;
    color: #888888;
  }

  .btn{
    width: 230rpx;
    margin: auto;
    padding: 8rpx 26rpx;
    font-weight: 600;
    font-size: 24rpx;
    line-height: 34rpx;
    border-radius: 25rpx;
    color: white;
    background-color: #3C4043;
  }
}
</style>
