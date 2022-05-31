<template>
  <div class="content-well-chosen-page">
    <img class="image" src="https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/content-well-chosen.png" alt="">

    <article class="detail-info">
      <header class="header">{{ contentData.title }}</header>
      <section class="desc">
        <p
          v-for="(item,index) in contentData.paraData"
          :key="index"
          class="para"
        >
          {{ item }}
        </p>

      </section>

    </article>

    <section class="relative-goods">
      <header class='header'>相关藏品</header>
      <ul class="goods-list">
        <li
          class="goods-item"
          v-for="(item,index) in relativeGoods"
          :key="index"
        >
          <goodsItem  class="item" :goods-item="item"/>
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
import goodsItem from "@/components/goods-item";
export default {
  name: "content-well-chosen",
  components:{ goodsItem },
  data(){
    return {
      contentData:{
        title:'关于中国电影资料馆',
        paraData:[
          '国家电影档案馆，1958年成立，1980年成为国际电影资料馆联合会(FIAF) 正式会员。1984年组建中国电影艺术研究中心，两块牌子共同运行。',
          '成立至今，中国电影资料馆保存有各个时期的中外故事片、舞台艺术片、美术片、科教片、纪录片四万余部，电影文图档案十万余卷。而建馆六十多年来，中国电影资料馆也逐步发展成为以电影档案工作为核心、业务和功能多元化的电影文化机构，在中外电影档案的收集、保存、整理、研究、利用、交流等方面做出了积极贡献。',
          '近年来，中国电影资料馆积极推进数字化工作:对电影档案进行数字化转换、存储、修复、编研、传播，” 电影档案影 片数字化修护工程”、临“ 安溪数字资源中心”、融媒体中心等以数字化赋能，在保护文化遗产、创新文化样态方面秉持新发展理念，积极推动创新开发工作，用数字化形式激发文化创造活力，让传统文化资源绽放崭新魅力。8《劳工之爱情》数字藏品是中国电影资料馆开发的首部系列数字藏品，是以“ 数字化+文化创意”引领潮流的一次有益尝试。'
        ]
      },
      relativeGoods:[
        {
          title:'劳工之爱情-郑木匠',
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/relative.png',
          price:100.00
        },
        {
          title:'劳工之爱情-郑木匠',
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/relative.png',
          price:100.00
        },
        {
          title:'劳工之爱情-郑木匠',
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/relative.png',
          price:100.00
        },
        {
          title:'劳工之爱情-郑木匠',
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/relative.png',
          price:100.00
        }
      ]
    }
  }

}
</script>

<style scoped lang="scss">
.content-well-chosen-page{
  background: #1E201F;
  padding-bottom: 100rpx;
  .detail-info{
    margin: 20rpx 32rpx;
    border: 3px solid #F2E1BD;
    .header{
      text-align: center;
      border: 3px solid #F2E1BD;
      font-weight: 600;
      font-size: 36rpx;
      line-height: 74rpx;
    }

    .desc{
      font-weight: 600;
      font-size: 24rpx;
      line-height: 34rpx;
      padding: 19rpx 26rpx 33rpx;
      .para{
        font-weight: 600;
        font-size: 24rpx;
        line-height: 34rpx;
        &:not(:last-child){
          margin-bottom: 20rpx;
        }

      }

    }
  }

  .relative-goods{
    margin: 10rpx 32rpx 20rpx;
    .header{
      font-weight: 600;
      font-size: 36rpx;
      line-height: 50rpx;
      margin: 20rpx 0 30rpx;
    }
    .goods-item{
      &:not(:last-child){
        margin-bottom: 25rpx;
      }

      .item:not(:last-child){
        margin-bottom: 20rpx;
      }
    }
  }
}

</style>
