<template>
  <div class="release-page">
    <div class="release-control">
      <span class="cancel" @click="cancel">取消</span>
      <span class="release" @click="release">发布</span>
    </div>
    <p class="desc">有趣的内容会有更多赞哦...</p>

    <div class="add-wrapper">
      <div class="add" @click="add">
        <uni-icons
          class="icon"
          color="#D9D9D9"
          custom-prefix="iconfont"
          type="icon-add"
          size="22"
        />
      </div>
    </div>

  </div>
</template>

<script>
import { uniIcons } from '@dcloudio/uni-ui'
export default {
  name: "release",
  data(){
    return {

    }
  },
  computed:{

  },
  components:{  uniIcons },
  created() {

  },
  methods:{
    cancel(){
      console.log('cancel')
      uni.navigateBack()
    },
    release(){
      console.log('release')
    },
    add(){
      console.log('add')
    }
  }
}
</script>

<style scoped lang="scss">
.release-page{
  padding: 88rpx 58rpx 0;
  .release-control{
    display: flex;
    justify-content: space-between;
    margin: 14rpx 0;
    font-size: 24rpx;
    line-height: 34rpx;
    .release{
      width: 110rpx;
      height: 36rpx;
      background: #F2E1BD;
      border-radius: 18rpx;
      text-align: center;
      color: black;
    }
  }

  .desc{
    margin: 34rpx 0 15rpx;
    font-size: 24rpx;
    line-height: 34rpx;
    color: #888888;
  }

  .add-wrapper{
    padding: 70rpx 0;
    border-bottom: 1rpx solid #888888;
    .add{
      display: flex;
      justify-content: center;
      align-items: center;
      width: 175rpx;
      height: 175rpx;
      background-color: #4E4E4E;
    }
  }
}
</style>
