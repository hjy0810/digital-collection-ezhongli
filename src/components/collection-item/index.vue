<template>
  <div class="collection-item-wrapper">
    <img class="image" :src="itemInfo.imgUrl" alt="">
    <div class="detail">
      <p class="title ellipsis">{{ itemInfo.title }}</p>
      <p class="id ellipsis">{{ itemInfo.id }}</p>
      <p class="company ellipsis">{{ itemInfo.company }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "collection-item",
  data(){
    return {
      // itemInfo:{
      //   imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%402x.png',
      //   title:'518纪念徽章',
      //   id:'AC554236#4421AC554236#4421AC554236#4421AC554236#4421AC554236#4421',
      //   company:'杭州众力网络科技杭州众力网络科技杭州众力网络科技杭州众力网络科技',
      // }
    }
  },
  props:{
    itemInfo:{
      type:Object,
      required: true
    }
  },
  computed:{

  },
  created() {

  },
  methods(){

  }
}
</script>

<style scoped lang="scss">
.collection-item-wrapper{
  background-color: #252726;
  border-radius: 40rpx;

  .image{
    border-radius: 40rpx;
    overflow: hidden;
  }

  .detail{
    padding: 40rpx 26rpx;

    .title{
      font-weight: 600;
      font-size: 24rpx;
      line-height: 34rpx;
    }

    .id{
      margin: 17rpx 0;
      padding: 0 30rpx;
      font-size: 20rpx;
      line-height: 28rpx;
      color: #CF703A;
      background: #FFDE9E;
      border-radius: 10rpx;
    }

    .company{
      font-weight: 600;
      font-size: 24rpx;
      line-height: 34rpx;
    }
  }
}
</style>
