<template>
  <div class="goods-item-wrapper">
    <img class="image" :src="goodsItem.imgUrl" alt="">
    <div class="item-info">
      <p class="title">{{ goodsItem.title }}</p>
      <Badge class="badge" title="限量" :count="goodsItem.count ? goodsItem.count : null" />
      <p class="price">￥ {{ goodsItem.price }}</p>
    </div>
  </div>
</template>

<script>
import Badge from "@/components/badge";
export default {
  name: "goods-item",
  components:{Badge},
  props:{
    goodsItem:{
      type:Object,
      required:true
    }
  }
}
</script>

<style scoped lang="scss">
.goods-item-wrapper{
  background-color: #323334;
  border-radius: 10rpx;
  overflow: hidden;
  display: grid;
  grid-template-columns: 182rpx auto;
  .image{
    width: 182rpx;
    border-radius: 10rpx;
  }
  .item-info{
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    margin-left: 20rpx;
    margin-right: 10rpx;
    justify-content: space-evenly;
    .title{
      font-weight: 600;
      font-size: 32rpx;
      line-height: 45rpx;
      /* TODO:单行文本省略号失效？ */
      overflow: hidden;
      text-overflow: ellipsis;
      display:-webkit-box; //作为弹性伸缩盒子模型显示。
      -webkit-box-orient:vertical; //设置伸缩盒子的子元素排列方式--从上到下垂直排列
      -webkit-line-clamp:1; //显示的行
    }

    .price{
      font-weight: 600;
      font-size: 36rpx;
      line-height: 50rpx;
    }
  }
}
</style>
