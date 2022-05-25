<template>
  <span class="badge-wrapper">
    <span class='badge'>{{ title }}</span>
    <span class="count" v-if="count">{{ count }}份</span>
  </span>
</template>

<script>
export default {
  name: "badge",
  props:{
    title:{
      type:String,
      required:true
    },
    count:{
      type:[Number,String],
      default:null
    }
  }
}
</script>

<style scoped lang="scss">
.badge-wrapper{
  margin-right: 20rpx;
  color: black;
  .badge,
  .count{
    padding: 0 19rpx;
    background-color: #F2E1BD;
    font-size: 20rpx;
    font-weight: 600;
  }
  .count{
    background-color: #888888;
    color:#F2E1BD;
  }
}
</style>
