<template>
  <div class="my-record-page">
    <ul class="record-list">
      <li
        class="item"
        v-for="(item,index) in collectionData"
        :key="index"
      >
        <div class="avatar">
          <img class="image" :src="item.imgUrl" alt="">
          <div class="info">
            <p class="title ellipsis">{{ item.title }}</p>
            <p class="label ellipsis">{{ item.label }}</p>
          </div>
          <p class="status">交易成功</p>
        </div>

        <p class="detail">
          <span class="key">交易时间</span>
          <span class="value">{{ item.time }}</span>
        </p>

        <p class="detail">
          <span class="key">记录单号</span>
          <span class="value">{{ item.recordId }}</span>
        </p>
      </li>
    </ul>

    <p class="no-record">
      <i></i>
      <span>没有更多记录了</span>
      <i></i>
    </p>



  </div>
</template>

<script>
export default {
  name: "my-record",
  data(){
    return {
      collectionData:[
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%401x.png',
          title:'518纪念徽章',
          label:'AC23213#dwefew',
          time:'2022-05-19 22:43:32',
          recordId:'2022051943231731672182',
          status:1
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%401x.png',
          title:'518纪念徽章',
          label:'AC23213#dwefew',
          time:'2022-05-19 22:43:32',
          recordId:'2022051943231731672182',
          status:1
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%401x.png',
          title:'518纪念徽章',
          label:'AC23213#dwefew',
          time:'2022-05-19 22:43:32',
          recordId:'2022051943231731672182',
          status:1
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%401x.png',
          title:'518纪念徽章',
          label:'AC23213#dwefew',
          time:'2022-05-19 22:43:32',
          recordId:'2022051943231731672182',
          status:1
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-2%401x.png',
          title:'518纪念徽章',
          label:'AC23213#dwefew',
          time:'2022-05-19 22:43:32',
          recordId:'2022051943231731672182',
          status:1
        },
      ]
    }
  },
  computed:{

  },
  created() {

  },
  methods:{

  }
}
</script>

<style scoped lang="scss">
.my-record-page{
  overflow: hidden auto;
  min-height: 100%;
  padding:10rpx 32rpx 100rpx;
  background-color: black;
  .record-list{
    .item{
      padding: 50rpx 26rpx 0;
      background-color: #252726;
      margin-bottom: 25rpx;
      border-radius: 10rpx;
      .avatar{
        /* TODO: 溢出时宽度问题 */
        display: grid;
        grid-template-columns: 74rpx auto 110rpx;
        grid-column-gap: 20rpx;
        grid-template-rows: 80rpx;
        align-items: center;
        padding-bottom:15rpx;
        border-bottom: 2px solid #2C2E2D;
        .image{
          width: 74rpx;
          height: 74rpx;
          border-radius: 10rpx;
          margin-right: 24rpx;
        }

        .info{
          margin-right: auto;
          .title{
            font-size: 32rpx;
            line-height: 45rpx;
          }

          .label{
            font-size: 24rpx;
            line-height: 34rpx;
            color: #888888;
          }
        }

        .status{
          width: 110rpx;
          font-size: 24rpx;
          color: #A8F4AA;
        }
      }

      .detail{
        display: flex;
        align-items: center;
        padding: 25rpx 0;
        &:nth-of-type(2){
          padding-top: 0;
        }

        .key{
          font-size: 32rpx;
          line-height: 45px;
        }

        .value{
          font-size: 24rpx;
          line-height: 34rpx;
          margin-left: auto;
        }
      }
    }
  }

  .no-record{
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20rpx auto;
    font-size: 24rpx;
    line-height: 34rpx;
    color: #888888;
    span{
      margin: 0 10rpx
    }

    i{
      width: 20rpx;
      height: 3rpx;
      background-color: #888888;
    }
  }
}
</style>
