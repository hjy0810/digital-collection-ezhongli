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

      <li class="info-item" @click="showInputDialog">
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
    <uni-popup
      ref="popup"
      background-color="#000"
      @change="change"
      safe-area
      type="bottom"
      :mask-click="false"
    >
      <p class="popup-content" @click="toTakePhoto">拍摄</p>
      <p class="popup-content">
        <uni-file-picker limit="5" file-mediatype="all">从手机相册选择</uni-file-picker>
      </p>
      <p class="popup-content" @click="closePopup">取消</p>
    </uni-popup>

    <!--  昵称弹窗  -->
    <uni-popup
      ref="inputDialog"
      type="dialog"
    >
      <uni-popup-dialog
        ref="inputClose"
        mode="input"
        title="修改昵称"
        placeholder="支持2-16位中英文、数字"
        @confirm="dialogInputConfirm"
      />
    </uni-popup>

  </div>
</template>

<script>
// uni.showModal({
//   title: '是否删除合同1',//提示标题
//   editable:true,
//   placeholderText:"ssss",
//   cancelText: "取消", // 取消按钮的文字
//   confirmText: "删除", // 确认按钮文字
//   confirmColor:'#F54E40',//删除字体的颜色
//   cancelColor:'#000',//取消字体的颜色
//   success: function(res) {
//     if (res.confirm) {
//       that.delContractPort();
//     } else if (res.cancel) {
//
//     }
//   }
// });
import { uniIcons, uniPopup, uniTransition  } from '@dcloudio/uni-ui'
export default {
  name: "edit",
  data(){
    return {
      avatarUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
      nickName:'藏家X1dwddefq',
      describe:'TA还什么都没留下~',
    }
  },
  components:{ uniIcons, uniPopup, uniTransition },
  computed:{

  },
  created() {
    // uni.showToast({
    //   title: '标题',
    //   duration: 2000
    // });
  },
  methods:{
    showPopup() {
      this.$refs.popup.open()
    },
    closePopup() {
      this.$refs.popup.close()
    },
    showInputDialog(){
      this.$refs.inputDialog.open()

    },
    closeInputDialog(){
      this.$refs.inputDialog.close()

    },
    dialogInputConfirm(val){
      uni.showLoading({
        title: '2秒后会关闭'
      })

      setTimeout(() => {
        uni.hideLoading()
        console.log(val)
        this.nickName = val
        // 关闭窗口后，恢复默认内容
        this.$refs.inputDialog.close()
      }, 2000)
    },
    toTakePhoto(){
      this.$refs.popup.close()
      console.log('take photo')
    },
    change(e) {
      console.log('当前模式：' + e.type + ',状态：' + e.show);
    },
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

  /* 修改avatar popup */
  .popup-content {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 15rpx;
    height: 100rpx;
    background-color: #252726;
    font-size: 32rpx;
    line-height: 45rpx;
    color: #fff;
    &:nth-child(1){
      margin-bottom: 2rpx;
    }
    &:nth-child(2){
      margin-bottom: 10rpx;
    }
  }

  /* 修改nickname dialog */
  /* TODO: 无法取到dialog选择器 */
  .uni-popup-dialog{
   color: red;
  }
}
</style>
