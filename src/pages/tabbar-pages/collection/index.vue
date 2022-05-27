<template>
<div class="collection-page">
  <header class="header-wrapper">
    <p class="header">我的展馆</p>
    <span class="id">NO.00000000001</span>
  </header>

  <section class="collection-wrapper">
    <header class="collection-header">
      <span class="title">我的藏品</span>
      <span class="count">1</span>
      <uni-icons class="icon" color="#fff" custom-prefix="iconfont" type="icon-danpin" size="20"></uni-icons>
      <span class="time">时间</span>
    </header>
    <ul class="collection-list">
      <collection-item
        v-for="(item,index) in collectionData"
        :key="index"
        :item-info="item"
      />
    </ul>
  </section>
</div>
</template>

<script>
import { uniIcons } from '@dcloudio/uni-ui'
import CollectionItem from "@/components/collection-item";
export default {
  name: "collection",
  components:{ uniIcons, CollectionItem },
  data(){
    return {
      collectionData:[
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%402x.png',
          title:'518纪念徽章',
          id:'AC554236#4421AC554236#4421AC554236#4421AC554236#4421AC554236#4421',
          company:'杭州众力网络科技杭州众力网络科技杭州众力网络科技杭州众力网络科技',
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%402x.png',
          title:'518纪念徽章',
          id:'AC554236#4421AC554236#4421AC554236#4421AC554236#4421AC554236#4421',
          company:'杭州众力网络科技杭州众力网络科技杭州众力网络科技杭州众力网络科技',
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%402x.png',
          title:'518纪念徽章',
          id:'AC554236#4421AC554236#4421AC554236#4421AC554236#4421AC554236#4421',
          company:'杭州众力网络科技杭州众力网络科技杭州众力网络科技杭州众力网络科技',
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%402x.png',
          title:'518纪念徽章',
          id:'AC554236#4421AC554236#4421AC554236#4421AC554236#4421AC554236#4421',
          company:'杭州众力网络科技杭州众力网络科技杭州众力网络科技杭州众力网络科技',
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%402x.png',
          title:'518纪念徽章',
          id:'AC554236#4421AC554236#4421AC554236#4421AC554236#4421AC554236#4421',
          company:'杭州众力网络科技杭州众力网络科技杭州众力网络科技杭州众力网络科技',
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%402x.png',
          title:'518纪念徽章',
          id:'AC554236#4421AC554236#4421AC554236#4421AC554236#4421AC554236#4421',
          company:'杭州众力网络科技杭州众力网络科技杭州众力网络科技杭州众力网络科技',
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.collection-page{
  background: black;
  padding-bottom: 250rpx;
  .header-wrapper{
    height: 350rpx;
    background-color:#323639 ;
    overflow: auto;
    padding:  0 32rpx 140rpx;
    .header{
      margin-top: 65rpx;
      font-weight: 600;
      font-size: 40rpx;
      line-height: 56rpx;
    }

    .id{
      font-weight: 600;
      font-size: 20rpx;
      line-height: 28rpx;
      color: #888888;
    }
  }

  .collection-wrapper{
    margin-top: -50rpx;
    border-radius: 40rpx 40rpx 0 0;
    padding: 26rpx 32rpx;
    background-color: #101211;

    .collection-header{
      display: flex;
      align-items: center;
      .title{
        font-size: 36rpx;
        line-height: 50rpx;
      }

      .count{
        margin-right: auto;
        margin-left: 20rpx;
        width: 36rpx;
        height: 36rpx;
        border-radius: 50%;
        padding: 5rpx;
        background-color: #252726;
        text-align: center;
        font-weight: 600;
        font-size: 20rpx;
        line-height: 28rpx;
      }

      .time{
        margin-left: 22rpx;
        font-size: 32rpx;
        line-height: 45rpx;
      }
    }

    .collection-list{
      display: grid;
      grid-template-columns: 47% 47%;
      grid-auto-rows: auto;
      grid-gap: 3% 6%;
      padding: 20rpx 0;
    }
  }
}
</style>
