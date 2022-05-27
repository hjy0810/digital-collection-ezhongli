<template>
  <div :class="['container',{'is-hidden': curIndex === 1}]">
    <div class="banner">
      <img src="https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/banner%402x.png" alt="">
    </div>

    <ul class="main-nav">
      <li
        v-for="(item,index) in navInfo"
        :key="index"
        :class="['nav-items',{'is-select':index === curIndex}]"
        @click="changeIndex(index)"
      >{{ item }}</li>

    </ul>
    <section class="main-content">
      <!--  数字藏品  -->
      <div v-if="curIndex === 0" class="content-item item-1" @click="toCollectionPage">
        <img src="https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/white-duck-produce%402x.png" alt="">
        <div class="info">
          <div class="header">这是一个藏品名称这是一个藏品名称这是一个藏品名称这是一个藏品名称</div>
          <div>
            <Badge title="潮玩"/>
            <Badge title="限量" count="8000"/>
          </div>
          <div class="detail">
            <span class="author">作者</span>
            <span class="price">￥ 25.00</span>
          </div>
        </div>

      </div>

      <!--  发售日历  -->
      <div v-if="curIndex === 1" class="content-item item-2">
        <div class="header">近期发售计划</div>
        <ul class="sale-plan">
          <li
            class="plan-item"
            v-for="(item,index) in salePlanInfo"
            :key="index"
          >
            <div class="date-info">
              <p class="data">{{ item.date }}</p>
              <p class="detail-time">{{ item.detailTime }}</p>
            </div>
            <goodsItem
              v-for="(item1,index1) in item.goods"
              :key="index1"
              class="item"
              :goods-item="item1"
            />
          </li>
        </ul>

      </div>

      <!--  内容精选  -->
      <div v-if="curIndex === 2 " class="content-item item-3" >
        <img @click="toContentPage" class="image" src="https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/Showroom%402x.png" alt="">
        <div class="detail">
          <p class="title">中国电影资料馆</p>
          <p class="description">国家电影档案馆，1958年成立，1980年成为国际电影资料馆联合会(FIAF) 正式会员。1984年组建中国电影艺术研究中心，两块牌子共同运行。
            成立至今，中国电影资料馆保存有各个时期的中外故事片、舞台艺术片、美术片、科教片、纪录片四万余部，电影文图档案十万余卷。而建馆六十多年来，中国电影资料馆也逐步发展成为以电影档案工作为核心、业务和功能多元化的电影文化机构，在中外电影档案的收集、保存、整理、研究、利用、交流等方面做出了积极贡献。
            近年来，中国电影资料馆积极推进数字化工作:对电影档案进行数字化转换、存储、修复、编研、传播，” 电影档案影 片数字化修护工程”、临“ 安溪数字资源中心”、融媒体中心等以数字化赋能，在保护文化遗产、创新文化样态方面秉持新发展理念，积极推动创新开发工作，用数字化形式激发文化创造活力，让传统文化资源绽放崭新魅力。8《劳工之爱情》数字藏品是中国电影资料馆开发的首部系列数字藏品，是以“ 数字化+文化创意”引领潮流的一次有益尝试。</p>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import Badge from "@/components/badge";
import goodsItem from "@/components/goods-item";
export default {
  components: {
    Badge,
    goodsItem
  },
  data(){
    return {
      navInfo:['数字藏品','发售日历','内容精选'],
      curIndex:1,
      salePlanInfo:[
        {
          date:'05月24日',
          detailTime:'12:00',
          goods:[
            {
              title:'小刘鸭',
              imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/whiteduck%402x.png',
              count:2000,
              price:100.00
            },
            {
              title:'小刘鸭等红吧鸭小刘鸭等红吧鸭小刘鸭等红吧鸭',
              imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/whiteduck%402x.png',
              count:4000,
              price:50.00
            },
          ]
        },
        {
          date:'05月24日',
          detailTime:'12:00',
          goods:[
            {
              title:'小刘鸭',
              imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/whiteduck%402x.png',
              count:2000,
              price:100.00
            },
            {
              title:'小刘鸭等红吧鸭小刘鸭等红吧鸭小刘鸭等红吧鸭',
              imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/whiteduck%402x.png',
              count:4000,
              price:50.00
            },
          ]
        },
        {
          date:'05月24日',
          detailTime:'12:00',
          goods:[
            {
              title:'小刘鸭',
              imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/whiteduck%402x.png',
              count:2000,
              price:100.00
            },
            {
              title:'小刘鸭等红吧鸭小刘鸭等红吧鸭小刘鸭等红吧鸭',
              imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/whiteduck%402x.png',
              count:4000,
              price:50.00
            },
          ]
        },
        {
          date:'05月25日',
          detailTime:'12:00',
          goods:[
            {
              title:'小刘鸭等红吧鸭小刘鸭等红吧鸭小刘鸭等红吧鸭',
              imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/whiteduck%402x.png',
              count:8000,
              price:25.00
            },
            {
              title:'小刘鸭等红吧鸭小刘鸭等红吧鸭小刘鸭等红吧鸭',
              imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/whiteduck%402x.png',
              count:8000,
              price:25.00
            },
          ]
        }
      ]



    }
  },
  mounted() {

  },
  computed: {

  },
  methods: {
    changeIndex(index){
      this.curIndex = index
    },
    /* 跳转 */
    toCollectionPage(){
      uni.navigateTo({
        url:'/pages/collection-detail/index'
      })
    },
    toContentPage(){
      uni.navigateTo({
        url:'/pages/content-well-chosen/index'
      })
    }

  }
}
</script>

<style scoped lang="scss">
.container{
  margin-bottom: 135rpx;
  padding: 0 32rpx 135rpx;
  &.is-hidden{
    overflow: hidden;
  }
  .banner{
    img{
      width: 100%;
      margin-top: 14rpx;
    }
  }

  .main-nav{
    display: flex;
    margin:40rpx auto;
    line-height: 50rpx;
    font-size: 36rpx;
    color: #888;
    .nav-items{
      flex: 1;
      &.is-select{
        color:white;
      }
    }
  }

  .main-content{
    .content-item{
      overflow: hidden;
    }

    .item-1{
      background-color: #333;
      border-radius: 40rpx;
      padding-bottom: 20rpx;
      img{
        width: 100%;
      }

      .info{
        padding: 0 26rpx;
        .header{
          font-size: 36rpx;
          line-height: 50rpx;
          margin: 20rpx 0;
          white-space: nowrap;
          overflow: hidden;
          text-overflow: ellipsis;
        }
      }

      .detail{
        display: flex;
        justify-content: space-between;
        margin:34rpx 0 10rpx 0;
        .author::before{
          display: inline-block;
          content: '';
          width: 26rpx;
          height: 26rpx;
          border-radius: 50%;
          background-color: #888;
          margin-right: 12rpx;
        }
      }


    }

    .item-2{
      overflow: auto;
      border-radius: 10rpx;
      .header{
        /*TODO*/
        //position: sticky;
        //top: 0;
        font-weight: 600;
        font-size: 36rpx;
        line-height: 50rpx;
        color: #F3E1BD;
        margin-bottom: 20rpx;
      }

      .sale-plan{
        background-color: #2A2E2F;
        .plan-item{
          &:not(:last-child){
            margin-bottom: 60rpx;
          }
          .date-info{
            padding: 16rpx 26rpx 23rpx;
            .date{
              font-weight: 600;
              font-size: 32rpx;
              line-height: 45rpx;
            }

            .detail-time{
              font-weight: 600;
              font-size: 24rpx;
              line-height: 34rpx;
            }

          }

          .item:not(:last-child){
            margin-bottom: 20rpx;
          }
        }
      }
    }

    .item-3{
      border-radius: 20rpx;
      background-color: #1E201F;
      .image{
        width: 100%;
      }
      .detail{
        padding: 20rpx 26rpx 10rpx;
        .title{
          font-weight: 600;
          font-size: 36rpx;
          line-height: 50rpx;
        }
        .description{
          font-weight: 600;
          font-size: 24rpx;
          line-height: 34rpx;
          overflow: hidden;
          text-overflow: ellipsis;
          display:-webkit-box; //作为弹性伸缩盒子模型显示。
          -webkit-box-orient:vertical; //设置伸缩盒子的子元素排列方式--从上到下垂直排列
          -webkit-line-clamp:3; //显示的行
        }
      }
    }
  }
}

</style>
