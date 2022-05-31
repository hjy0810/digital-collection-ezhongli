<template>
  <div class="my-like-page">
    <div style="height: 100%">
      <ul class="main-nav">
        <li
          v-for="(item,index) in navInfo"
          :key="index"
          :class="['nav-items',{'is-select':index === curIndex}]"
          @click="changeIndex(index)"
        >{{ item }}</li>
      </ul>

      <section class="main-content">
        <!--  藏品  -->
        <div v-if="curIndex === 0" class="content-item item-1">
          <None>
            <template #title>
              <p class="title">这里空空的</p>
              <p class="desc">你还没有喜欢过的藏品哦</p>
            </template>
            <template #button>
              <button class="btn" @click="toDiscover">去发现页看看</button>
            </template>
          </None>
        </div>

        <!--  话题  -->
        <div v-if="curIndex === 1" class="content-item item-2">
          <None>
            <template #title>
              <p class="title">这里空空的</p>
              <p class="desc">去话题广场发现你感兴趣的话题吧</p>
            </template>
            <template #button>
              <button class="btn" @click="toTopicSquare">去话题广场看看</button>
            </template>
          </None>

        </div>

      </section>
    </div>
  </div>
</template>

<script>
import None from '@/pages/none/index'
export default {
  name: "my-like",
  components:{ None },
  data(){
    return {
      curIndex: 0,
      navInfo:['藏品','话题'],


    }
  },
  computed:{

  },
  created() {

  },
  methods:{
    changeIndex(index){
      this.curIndex = index
    },
    toDiscover(){
      uni.switchTab({
        url:'/pages/tabbar-pages/discover/index'
      })
      console.log('dis')
    },
    toTopicSquare(){
      console.log('squ')
    }

  }
}
</script>

<style scoped lang="scss">
.my-like-page{
  background-color: black;
  height: 100%;
  padding: 0 32rpx;
  .main-nav{
    display: flex;
    line-height: 50rpx;
    font-size: 36rpx;
    color: #888;
    padding: 5rpx 0;
    border-bottom: 1rpx solid #888888;
    .nav-items{
      position: relative;
      margin-right: 50rpx;
      &.is-select{
        color:white;
      }
      &.is-select::after{
        position: absolute;
        bottom: -6rpx;
        left: 0;
        display: block;
        content: '';
        width: 100%;
        height: 5px;
        background-color: white;
      }
    }
    //&::after{
    //  display: block;
    //  content: '';
    //  height: 1px;
    //  background-color: ;
    //}
  }

  .main-content{
    //background-color: #000;
    //.content-item{
    //  overflow: hidden;
    //}
    //}
  }
}
</style>
