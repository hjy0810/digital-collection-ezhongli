<template>
  <div class="my-home-page">
    <header class="header-wrapper">
      <div class="top-icon">
        <uni-icons
          class="icon"
          color="#fff"
          custom-prefix="iconfont"
          type="icon-arrow-left"
          @click="back"
        />
        <span @click="toEditPage">编辑资料</span>
      </div>

      <div class="bottom-info">
        <img class="image" :src="userInfo.imgUrl" alt="">
        <div class="detail">
          <p class="nickname">{{ userInfo.nickname }}</p>
          <span class="num">{{ userInfo.fanNumber }}粉丝</span>
          <span class="num">{{ userInfo.careNumber }}关注</span>
        </div>
      </div>
    </header>

    <div class="main-content">
      <div class="col-card">
        <p class="introduction">{{ userInfo.introduction }}</p>
        <div class="display">
          <p class="title">藏家_7ded12342de的展馆</p>
          <div class='col-info'>
            <p class="title">GALLERY</p>
            <p class="id">NO.000000213</p>
            <i class="dot"></i>
            <i class="dot"></i>
            <i class="dot"></i>
            <i class="dot"></i>
          </div>
          <span class="displaying">正在展览</span>
        </div>
      </div>

      <p class="recently">动态</p>
      <None class="none">
        <template #title>
          <p class="title">精彩待发生</p>
          <p class="desc">寻找感兴趣的话题，发表你有趣的观点吧</p>
        </template>
      </None>
    </div>
  </div>
</template>

<script>
import { uniIcons } from '@dcloudio/uni-ui'
import None from '@/pages/none'
export default {
  name: "my-home",
  data(){
    return {
      userInfo:{
        imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
        nickname:"藏家X1dwddefq",
        fanNumber:100,
        careNumber:200,
        introduction:'TA还什么都没留下~'
      }
    }
  },
  components:{ uniIcons, None },
  computed:{

  },
  created() {

  },
  methods:{
    /* 跳转相关 */
    back(){
      uni.navigateBack()
    },
    toEditPage(){
      uni.navigateTo({
        url:'/pages/edit/index'
      })
    }

  }
}
</script>

<style scoped lang="scss">
.my-home-page{
  min-height: 100%;
  background: black url("https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/home-bg.png") no-repeat;
  background-size: contain;
  .header-wrapper{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 88rpx 32rpx 0;
    height: 440rpx;
    .top-icon{
      display: flex;
      justify-content: space-between;
    }

    .bottom-info{
      display: flex;
      align-items: center;
      .image{
        width: 120rpx;
        height: 120rpx;
        border-radius: 50%;
      }

      .detail{
        margin-left: 35rpx;
        .nickname{
          font-size: 36rpx;
          line-height: 50rpx;
        }

        .num{
          font-size: 24rpx;
          line-height: 34rpx;
          &:last-child{
            padding-left: 20rpx;
          }
        }
      }
    }
  }

  .main-content{
    padding: 20rpx 26rpx;
    .col-card{
      .introduction{
        line-height: 85rpx;
        font-size: 32px;
        border-radius: 0 36rpx;
        padding-left:60rpx;
        background-color: #252726;
      }

      .display{
        overflow: auto;
        margin: 20rpx 0;
        padding: 26rpx;
        background-color: #252726;
        border-radius: 10rpx;
        .title{
          font-size: 32rpx;
          line-height: 45rpx;
        }

        .col-info{
          position: relative;
          margin: 11rpx 0 24rpx;
          padding: 10rpx;
          background: linear-gradient(90deg, #FFD06C 0%, #FEDB99 52.59%, #FFE9C0 100%);
          max-width: 50%;
          text-align: center;
          border-radius: 10rpx;
          color: #CF703A;
          .title{
            font-size: 16rpx;
            line-height: 22rpx;
          }
          .id{
            font-size: 24rpx;
            line-height: 34rpx;
          }
          .dot{
            position: absolute;
            width: 6rpx;
            height: 6rpx;
            border-radius: 50%;
            background-color: #CF703A;
            &:nth-of-type(1){
              left: 10rpx;
              top: 10rpx;
            }
            &:nth-of-type(2){
              left: 10rpx;
              bottom: 10rpx;
            }
            &:nth-of-type(3){
              right: 10rpx;
              top: 10rpx;
            }
            &:nth-of-type(4){
              right: 10rpx;
              bottom: 10rpx;
            }
          }
        }

        .displaying{
          font-weight: 600;
          font-size: 16px;
          line-height: 22px;
          padding: 5rpx 17rpx;
          color: #A8F4AA;
          background-color: #3F4140;
          border-radius: 10rpx;

          &::before{
            display: inline-block;
            content: '';
            vertical-align: middle;
            margin-right: 18rpx;

            width: 6rpx;
            height: 6rpx;
            border-radius: 50%;
            background-color:#A8F4AA;
          }
        }
      }
    }
  }

  .recently{
    font-size: 36rpx;
    line-height: 50rpx;
    padding-bottom: 10rpx;
    //width: 72rpx;
    border-bottom: 1px solid #2C2E2D;
    &::after{
      position: relative;
      display: block;
      bottom:-12rpx;
      content: '';
      width: 72rpx;
      height: 3rpx;
      background-color: white;
    }
  }

  .none{
    padding-top: 50rpx;
  }
}
</style>
