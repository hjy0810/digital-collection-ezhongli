<template>
  <view class="container">
    <!--  popup  -->
      <uni-popup ref="popup" type="bottom" background-color="#fff">
        <view class="popup-content">
          <text class="text">popup 内容</text>
        </view>
        <view class="popup-content">
          <text class="text">popup 内容</text>
        </view>
      </uni-popup>
  </view>
</template>
<script>
// 这里不用import引入，也不需要在components内注册uni-list组件。template里就可以直接用
export default {
  name: "popup",
  data() {
    return {
      showPopup:''

    }
  },
  watch:{
    show(newV){
      this.showPopup = newV
      this.$refs.popup.open()

      console.log('change')
    }
  }

}
</script>

<style scoped>

</style>
