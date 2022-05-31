<template>
  <div class="collection-page">
    <uni-icons
      class="back-icon"
      color="#fff"
      custom-prefix="iconfont"
      type="icon-arrow-left"
      size="24"
      @click="back"
    />
    <img class="goods" src="https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/mask-group%20.png" alt="">

    <div class="state">
      <img src="https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/booth%402x.png" alt="">
      <div class="content">
        <img src="https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/ear%402x.png" alt="">
        <div class="title">小刘鸭-等红包鸭</div>
        <p>
          <Badge title="潮玩"/>
          <Badge title="限量" count="8000"/>
        </p>
      </div>
      <div class="vip">
        <uni-icons color="#888" custom-prefix="iconfont" type="icon-locked" size="10"></uni-icons>
        <p class="purchase">购买即可体验内容</p>
      </div>
    </div>

    <div class="avatar-info">
      <img class="image" src="https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png" alt="">
      <div class="detail">
        <p class="title">杭州众力</p>
        <p class="order">作品1</p>
      </div>
      <button class="btn">
        <uni-icons color="#000" custom-prefix="iconfont" type="icon-add" size="14"></uni-icons>
        关注
      </button>
    </div>

    <div class="story">
      <p class="title">作品故事</p>
      <img class="image" src="https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/story%402x.png" alt="">
    </div>
    <p class="description">
      数字藏品为虚拟数字商品，而非实物，仅限实名认证为年满14周岁的中国大陆用户购买。数字藏品的版权由发行方或原创者拥有，除另行取得版权拥有者书面同意外，用户不得将数字藏品用于任何商业用途。本商品一经售出，不支持退换。本商品源文件不支持本地下载。请勿对数字藏品进行炒作、场外交易、欺诈，或以任何其他非法方式进行使用。
    </p>

    <div class="purchase">
      <div class="price">
        <uni-icons color="#fff" custom-prefix="iconfont" type="icon-rmb" size="24"></uni-icons>
        <span>25.00</span>
      </div>
      <button class="btn">
        <span>设置购买提醒</span>
        <uni-countdown
          :day="1"
          :hour="1"
          :minute="12"
          :second="40"
          color="#CF703A"
          splitorColor="#CF703A"
          :font-size="10"
        ></uni-countdown>
      </button>
    </div>
  </div>
</template>

<script>
import {
  uniNavBar,
  uniIcons,
  uniFav,
  uniCountdown
} from '@dcloudio/uni-ui'
import Badge from '@/components/badge'
export default {
  name: "collection-detail",
  components: {uniNavBar, uniIcons,uniFav,uniCountdown, Badge },
  created () {
    // console.log(this)

  },
  methods:{

    /* 路由相关 */
    back(){
      uni.navigateBack()
    }
  }
}
</script>

<style scoped lang="scss">
.collection-page{
  position: relative;
  margin-bottom: -135rpx;
  background: #000 url(https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/shine%402x.png) top center no-repeat;
  background-size: 50%;
  text-align: center;
  .back-icon{
    position: fixed;
    left: 26rpx;
    top: 80rpx;
  }
  img{
    width: 50%;
  }

  .goods{
    margin-top: 500rpx;
  }

  .state{
    position: relative;
    overflow: hidden;
    height: 400rpx;
    img{
      position: absolute;
      margin: auto;
      left: 0;
      right: 0;
      width: 80%;
    }

    .content{
      position: relative;
      margin-top: 150rpx;
      height: 55rpx;
      img{
        width: 70%;
      }

      .title{
        font-weight: 600;
        font-size: 36rpx;
        line-height: 50rpx;
        margin-bottom: 10rpx;
      }
    }

    .vip{
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 60rpx;
      color: #888;
      .purchase{
        margin: 0;
        padding-left: 5rpx;
        padding-right: 5rpx;
        font-size: 20rpx;
        line-height: 28rpx;
      }
      &::before,
      &::after{
        position: absolute;
        left:50%;
        //top: 15rpx;
        top: 50%;
        display: inline;
        content: '';
        margin: auto;
        width: 20%;
        border-bottom:1px solid #888;
      }
      &::before{
        transform: translateX(-200%);
      }
      &::after{
        transform: translateX(100%);
      }
    }


  }

  .avatar-info{
    display: flex;
    margin: 0 32rpx;
    align-items: center;
    height: 120rpx;
    padding: 21rpx 26rpx;
    background-color: #252726;
    .image{
      width: 74rpx;
      height:74rpx;
      border-radius: 50%;
    }

    .detail{
      margin-left: 24rpx;
      margin-right: auto;
      font-size: 24rpx;
      line-height: 34rpx;
      text-align: left;
      .order{
        color:#888;
      }
    }

    .btn{
      width: 148rpx;
      line-height:60rpx;
      border-radius: 30rpx;
      background-color: #F3E1BD;
      font-weight: 600;
    }
  }

  .story{
    margin: 18rpx 32rpx;
    padding: 26rpx;
    background: #252726;
    border-radius: 10px;
    .title{
      text-align: left;
      font-weight: 600;
      font-size: 36rpx;
      line-height: 50rpx;
      margin-bottom: 10rpx;
    }

    .image{
      width: 100%;
    }
  }

  .description{
    margin: 18rpx 32rpx;
    padding: 36rpx 26rpx;
    background: #252726;
    text-align: justify;
    border-radius: 10rpx;
    font-weight: 600;
    font-size: 20rpx;
    line-height: 28rpx;
  }

  .purchase{
    display: flex;
    justify-content: space-between;
    margin: 18rpx 32rpx;
    padding: 36rpx 26rpx;
    .price{
      font-weight: 600;
      font-size: 48rpx;
      line-height: 67rpx;
    }

    .btn{
      display: flex;
      flex-direction: column;
      justify-content: space-evenly;
      align-items:  center;
      background: #F3E1BD;
      border-radius: 39rpx;
      font-weight: 600;
      font-size: 24rpx;
      line-height: 34rpx;
      color: #CF703A;
      padding: 10rpx 100rpx;
    }
  }
}
</style>
