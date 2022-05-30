<template>
  <div class="edit-page">
    <ul class="info-list">
      <li class="info-item"  @click="showPopup">
        <span class="label">头像</span>
        <div class="right">
          <img class="image" :src="avatarUrl" alt="">
          <uni-icons class="icon" color="#fff" custom-prefix="iconfont" type="icon-arrow-right" size="20" />
        </div>
      </li>

      <li class="info-item">
        <span class="label">昵称</span>
        <div class="right">
          <span>{{ nickName }}</span>
          <uni-icons class="icon" color="#fff" custom-prefix="iconfont" type="icon-arrow-right" size="20" />
        </div>
      </li>

      <li class="info-item">
        <span class="label">个性签名</span>
        <div class="right">
          <span>{{ describe }}</span>
          <uni-icons class="icon" color="#fff" custom-prefix="iconfont" type="icon-arrow-right" size="20" />
        </div>
      </li>

      <li class="info-item">
        <span class="label">主题封面</span>
        <div class="right">
          <uni-icons class="icon" color="#fff" custom-prefix="iconfont" type="icon-arrow-right" size="20" />
        </div>
      </li>
    </ul>

    <!--  头像 popup  -->
    <popup :show="true"/>

  </div>
</template>

<script>
import { uniIcons, uniPopup, uniTransition  } from '@dcloudio/uni-ui'
export default {
  name: "edit",
  data(){
    return {
      avatarUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
      nickName:'藏家X1dwddefq',
      describe:'TA还什么都没留下~'
    }
  },
  components:{ uniIcons, uniPopup, uniTransition},
  computed:{

  },
  created() {
    // console.log(  uniIcons, uniPopup, )

  },
  methods:{
    change(e) {
      console.log('当前模式：' + e.type + ',状态：' + e.show);
    },
    showPopup() {
      const popupDom = this.$children.find(item => item.$refs.popup)
      // popupDom.$refs.popup.open()
    }
  }
}
</script>

<style scoped lang="scss">
.edit-page{
  padding: 32rpx 32rpx 100rpx;
  min-height: 100%;
  background-color: black;
  .info-list{
    display: flex;
    flex-direction: column;
    font-size: 24rpx;
    .info-item{
      display: flex;
      align-items: center;
      padding: 20rpx 12rpx 20rpx 26rpx;
      background-color: #252726;
      border-radius: 10rpx;
      &:not(:last-child){
        margin-bottom: 20rpx;
      }

      .label{
        margin-right: auto;
      }

      .right{
        display: flex;
        align-items: center;
        .image{
          width: 80rpx;
          height: 80rpx;
          border-radius: 50%;
        }

        .icon{
          margin-left: 20rpx;
        }
      }
    }
  }

  .popup-content {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 15px;
    height: 50px;
    background-color: #fff;
    .text {
      font-size: 12px;
      color: #333;
    }
  }
}
</style>
