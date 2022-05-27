<template>
  <div class="my-message-page">
    <nav class="nav-list">
      <div
        class="item"
        v-for="(item,index) in navInfo"
        :key="index"
        @click="item.handleClick"
      >
        <uni-icons class="icon" color="#fff" custom-prefix="iconfont" :type="'icon-' + item.icon" size="26"></uni-icons>
        <p class="label">{{ item.label }}</p>
      </div>
    </nav>

    <section class="system-info">
      <p class="title">系统消息</p>
      <p class="notice">很遗憾未抽 中XXXXXX 数字文创</p>
      <p class="desc">感谢你的参与，后续活动敬请期待！</p>
      <p class="detail">查看详情</p>
    </section>
  </div>
</template>

<script>
import {
  uniIcons,
} from '@dcloudio/uni-ui'
export default {
  name: "my-message",
  data(){
    return {
      navInfo:[
        {
          icon:'dianzan',
          label:'赞',
          handleClick:null
        },
        {
          icon:'guanzhu',
          label:'新增关注',
          handleClick:null
        },
        {
          icon:'comment',
          label:'评论',
          handleClick:null
        },
      ],
    }
  },
  components:{ uniIcons },
  computed:{

  },
  created() {

  },
  methods:{

  }
}
</script>

<style scoped lang="scss">
.my-message-page{
  min-height: 100%;
  padding: 50rpx 26rpx;
  background-color: black;
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
        font-size: 32rpx;
        line-height: 45rpx;
        margin-top: 22rpx;
        color: #888888;
      }
    }
  }

  .system-info{
    padding: 26rpx;
    font-size: 24rpx;
    line-height: 34rpx;
    background-color: #252726;
    border-radius: 10px;
    margin-top: 25rpx;
    .title{
      padding-left: 40rpx;
      margin-bottom: 36rpx;
    }

    .notice{
      font-size: 32rpx;
      line-height: 45rpx;
    }

    .desc{
      margin: 12rpx auto 30rpx;
      color: #888888;
    }

    .detail{
      border-top: 2px solid #323232;
      padding-top: 25rpx;
    }
  }
}
</style>
