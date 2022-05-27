<template>
  <div class="mine-page">
    <header class="header-wrapper">
      <uni-icons class="icon-scan" color="#fff" custom-prefix="iconfont" type="icon-scan" size="24"></uni-icons>
      <div class="avatar-wrapper">
        <img class="image" :src="userInfo.avatarUrl" alt="">
        <div class="user-info">
          <p class="nickname">{{ userInfo.nickName }}</p>
          <p class="phone">{{ userInfo.phone }}</p>
        </div>
        <button @click="toMyHome" class="btn">个人主页</button>
      </div>

      <div class="block-chain">
        <span class="id ellipsis">区块链地址: {{ userInfo.blockChainID }}</span>
        <uni-icons class="icon" color="#fff" custom-prefix="iconfont" type="icon-copy" size="24"></uni-icons>
      </div>
    </header>

    <nav class="nav-list">
      <div
        class="item"
        v-for="(item,index) in navInfo"
        :key="index"
        @click="item.handleClick"
      >
        <uni-icons class="icon" color="#fff" custom-prefix="iconfont" :type="'icon-' + item.icon" size="24"></uni-icons>
        <p class="label">{{ item.label }}</p>
      </div>
    </nav>

    <div class="list">
      <div
        class="item"
        v-for="(item,index) in listInfo"
        :key="index"
      >
        <uni-icons class="icon" color="#fff" custom-prefix="iconfont" :type="'icon-' + item.icon" size="22"></uni-icons>
        <span class="label">{{ item.label }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import {
  uniIcons,
} from '@dcloudio/uni-ui'
export default {
  name: "mine",
  data(){
    return {
      userInfo:{
        avatarUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
        nickName:'藏家X1dwddefq',
        phone:'151******07',
        blockChainID:'03ed04r32frf2efrgf2rfg4f23f2f32ed...'
      },
      navInfo:[
        {
          icon:'like',
          label:'我的喜欢',
          handleClick:this.toMyLike
        },
        {
          icon:'dingdan',
          label:'我的订单',
          handleClick:this.toMyOrder
        },
        {
          icon:'record',
          label:'藏品记录',
          handleClick:this.toMyCollection
        },
        {
          icon:'message',
          label:'消息',
          handleClick:this.toMyMessage
        },
      ],
      listInfo:[
        {
          icon:'search',
          label:'区块链信息查询'
        },
        {
          icon:'wodekefu',
          label:'我的客服'
        },
        {
          icon:'about',
          label:'关于平台'
        },
        {
          icon:'share',
          label:'分享平台'
        },
        {
          icon:'set',
          label:'设置'
        }
      ]
    }
  },
  components:{ uniIcons },
  computed:{

  },
  created() {

  },
  methods:{
    /* 跳转相关 */
    toMyLike(){
      uni.navigateTo({
        url:"/pages/my-like/index"

      })
    },
    toMyOrder(){
      uni.navigateTo({
        url:"/pages/my-order/index"
      })
    },
    toMyCollection(){
      uni.navigateTo({
        url:"/pages/my-record/index"
      })
    },
    toMyMessage(){
      uni.navigateTo({
        url:"/pages/my-message/index"
      })
    },
    toMyHome(){
      uni.navigateTo({
        url:"/pages/my-home/index"
      })
    }
  }
}
</script>

<style scoped lang="scss">
.mine-page{
  height: 100%;
  padding: 0 32rpx;
  background-color: black;
  .header-wrapper{
    overflow: auto;
    margin-bottom: 47rpx;
    position: relative;
    .icon-scan{
      position: absolute;
      top: 0;
      right: 32rpx;
    }

    .avatar-wrapper{
      display: flex;
      align-items: center;
      margin-top: 40rpx;
      .image{
        width: 120rpx;
        height: 120rpx;
        border-radius: 50%;
      }

      .user-info{
        margin-left: 35rpx;
        margin-right: auto;
        .nickname{
          font-size: 36rpx;
          line-height: 50rpx;
          margin-bottom: 8rpx;
        }

        .phone{
          font-size: 24rpx;
          line-height: 34rpx;
        }
      }

      .btn{
        width: 150rpx;
        line-height: 34rpx;
        padding: 8rpx 25rpx;
        border-radius: 25rpx;
        background-color: #3C4043;
        font-weight: 600;
        font-size: 24rpx;
        color: white;
      }
    }

    .block-chain{
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 53rpx;
      padding-top: 15rpx;
      border-top: 1px solid #2C2E2D;
      .id{
        font-weight: 600;
        font-size: 24rpx;
        line-height: 34rpx;
      }
      .icon{
        margin-left: 46rpx;
      }
    }
  }

  .nav-list{
    height: 180rpx;
    display: flex;
    justify-content: space-around;
    align-items: center;
    text-align: center;
    background-color: #252726;
    border-radius: 10px;
    .item{
      .label{
        font-size: 24rpx;
        line-height: 34rpx;
        margin-top: 22rpx;
        color: #888888;
      }
    }
  }

  .list{
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin-top: 20rpx;

    //border-radius: 10rpx;
    .item{
      padding: 0 30rpx;
      height: 120rpx;
      background-color: #252726;
      line-height: 120rpx;
      .label{
        font-size: 32rpx;
        //line-height: 45rpx;
        margin-left: 50rpx;
      }

      &:nth-child(-n+3)::after{
        content: '';
        display: block;
        height: 2rpx;
        margin-top: -8rpx;
        background-color: #2C2E2D;
      }

      &:first-child{
        border-radius: 10rpx 10rpx 0 0;
      }
      &:nth-child(4){
        border-radius: 0 0 10rpx 10rpx;
      }
      &:last-child{
        border-radius: 10rpx;
        margin-top: 20rpx;
      }
    }
  }
}
</style>
