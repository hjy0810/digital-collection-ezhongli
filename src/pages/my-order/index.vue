<template>
  <div class="my-order-page">
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
        <!--  全部订单  -->
        <div v-if="curIndex === 0" class="content-item item-1">
          <None>
            <template #title>
              <p class="title">你还没有相关订单</p>
              <p class="desc">这里将展示你在平台购买的数字藏品订单</p>
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
  name: "my-order",
  components:{ None },
  data(){
    return {
      curIndex: 0,
      navInfo:['全部','待付款','已付款','已取消'],


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
  }
}
</script>

<style scoped lang="scss">
.my-order-page{
  background-color: black;
  height: 100%;
  padding: 0 32rpx;
  .main-nav{
    display: flex;
    text-align: center;
    line-height: 50rpx;
    font-size: 36rpx;
    color: #888;
    padding: 5rpx 0;
    border-bottom: 1rpx solid #888888;
    .nav-items{
      flex:1;
      position: relative;
      &.is-select{
        color:white;
      }
      &.is-select::after{
        position: absolute;
        bottom: -6rpx;
        left: 0;
        right: 0;
        margin: auto;
        display: block;
        content: '';
        width: 70%;
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
