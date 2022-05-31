<template>
  <div class="discover-page">
    <uni-notice-bar
      class="notice-bar"
      show-icon
      scrollable
      text="社区功能内测中!社区功能内测中!社区功能内测中!社区功能内测中!社区功能内测中!"
    />

    <div class="main-content">
      <!--  热门话题  -->
      <div class="hot-topic">
        <header class="title">热门话题</header>
        <ul class="topic-list">
          <li
            class="topic-item"
            v-for="(item,index) in topicInfo"
            :key="index"
          >
            <img class="image" :src="item.imgUrl" alt="">
            <span class="label">{{ item.label }}</span>
          </li>
        </ul>
      </div>

      <!--  人气藏品    -->
      <div class="popular-goods">
        <header class="title-row">
          <span class="title">人气藏品</span>
          <span class="icon-wrapper" @click="more">更多
            <uni-icons
              class="icon"
              color="#888"
              custom-prefix="iconfont"
              type="icon-arrow-right"
              size="18"
            />
          </span>
        </header>
        <ul class="goods-list">
          <li
            class="goods-item"
            v-for="(item,index) in popularGoodsInfo"
            :key="index"
          >
            <img class="image" :src="item.imgUrl" alt="">
            <p class="label">{{ item.label }}</p>
          </li>
        </ul>
      </div>

      <!--  大家都在逛    -->
      <div class="all-like">
        <header class="title-row">
          <span class="title">大家都在逛</span>
          <span class="icon-wrapper" @click="change">换一换
            <uni-icons
              class="icon"
              color="#888"
              custom-prefix="iconfont"
              type="icon-huanyihuan"
              size="18"
            />
          </span>
        </header>
        <ul class="all-like-list">
          <li
            class="all-like-item"
            v-for="(item,index) in allLikeInfo"
            :key="index"
          >
            <div class="info">
              <p class="title ellipsis">{{ item.title }}</p>
              <p class="desc ellipsis">{{ item.desc }}</p>
              <div class="avatar-wrapper">
                <img class="image" :src="item.avatarUrl" alt="">
                <span class="nickname">{{ item.nickName }}</span>
              </div>
            </div>
            <img class="image" :src="item.imgUrl" alt="">
          </li>
        </ul>
      </div>

      <!--  精选动态    -->
      <div class="recent">
        <header class="title-row">
          <span class="title">精选动态</span>
          <span class="icon-wrapper" @click="change">换一换
            <uni-icons
              class="icon"
              color="#888"
              custom-prefix="iconfont"
              type="icon-huanyihuan"
              size="18"
            />
          </span>
        </header>
        <ul class="recent-list">
          <li
            class="recent-item"
            v-for="(item,index) in recentInfo"
            :key="index"
          >
            <div class="avatar-wrapper">
              <img class="image" :src="item.avatarUrl" alt="">
              <div class="detail">
                <p class="nick-name">{{ item.nickName }}</p>
                <span class="time">{{ item.time }}</span>
              </div>
            </div>
            <p class="content">{{ item.content }}</p>
            <ul class="image-list">
              <li class="item" v-for="(imgItem,i) in item.imgList" :key="i">
                <img :src="imgItem" alt="">
              </li>
            </ul>

            <div class="icon-wrapper">
              <div class="comment">
                <uni-icons
                  class="icon"
                  color="#888"
                  custom-prefix="iconfont"
                  type="icon-comment"
                  size="22"
                />
                {{ item.commentCount }}
              </div>

              <div class="thumb-up">
                <uni-icons
                  class="icon"
                  color="#888"
                  custom-prefix="iconfont"
                  type="icon-dianzan"
                  size="22"
                />
                {{ item.thumbUpCount }}
              </div>
            </div>
          </li>
        </ul>
      </div>

      <!--  发布按钮    -->
      <div class="release" @click="toRelease">
        <uni-icons
          class="icon"
          color="#000"
          custom-prefix="iconfont"
          type="icon-yongyan"
          size="18"
        />
      </div>
    </div>
  </div>
</template>

<script>
import { uniNoticeBar, uniIcons } from '@dcloudio/uni-ui'
export default {
  name: "discover",
  data(){
    return {
      topicInfo:[
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          label:'#人人都是产品经理人人都是产品经理人人都是产品经理人人都是产品经理'
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          label:'#人人都是产品经理'
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          label:'#人人都是产品经理'
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          label:'#人人都是产品经理'
        }
      ],
      popularGoodsInfo:[
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-1%402x.png',
          label:'正公子也正公子也正公子也正公子也'
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-1%402x.png',
          label:'正公子也'
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-1%402x.png',
          label:'正公子也'
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-1%402x.png',
          label:'正公子也'
        },
        {
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/produce-1%402x.png',
          label:'正公子也'
        }
      ],
      allLikeInfo:[
        {
          avatarUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/all-like.png',
          nickName:'疯狂小杨哥',
          title:'jingtan8008',
          desc:'有缘人直接转送哦'
        },
        {
          avatarUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/all-like.png',
          nickName:'疯狂小杨哥',
          title:'jingtan8008',
          desc:'有缘人直接转送哦'
        },
        {
          avatarUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/all-like.png',
          nickName:'疯狂小杨哥',
          title:'jingtan8008',
          desc:'有缘人直接转送哦'
        },
        {
          avatarUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          imgUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/all-like.png',
          nickName:'疯狂小杨哥',
          title:'jingtan8008',
          desc:'有缘人直接转送哦'
        },
      ], /* 大家都喜欢 */
      recentInfo:[
        {
          avatarUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          nickName:'周旭',
          time:'10个小时以前',
          content:'《人物御龙帛画》为2000多年前的“魂幡”，画面简洁而具有神秘意味，大多数学者认为这是一幅“导引灵魂升天”图。它保存较为完好，刻画生动，被称作“中国早期肖像画的杰出代表”',
          imgList:[
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo-1%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo-1%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo-1%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo%402x.png'
          ],
          commentCount:78,
          thumbUpCount:78
        },
        {
          avatarUrl:'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/pinkduck%402x.png',
          nickName:'周旭',
          time:'10个小时以前',
          content:'《人物御龙帛画》为2000多年前的“魂幡”，画面简洁而具有神秘意味，大多数学者认为这是一幅“导引灵魂升天”图。它保存较为完好，刻画生动，被称作“中国早期肖像画的杰出代表”',
          imgList:[
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo-1%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo-1%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo-1%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo%402x.png',
            'https://w1-dev.oss-cn-hangzhou.aliyuncs.com/photos/digital/initial/photo%402x.png'
          ],
          commentCount:78,
          thumbUpCount:78
        }
      ] /* 精选动态 */
    }
  },
  components:{ uniNoticeBar, uniIcons },
  computed:{

  },
  created() {

  },
  methods:{
    change(){
      console.log('change')
    },
    /* 跳转 */
    more(){
      console.log('more')
    },
    toRelease(){
      uni.navigateTo({
        url:'/pages/release/index'
      })
    }
  }
}
</script>

<style scoped lang="scss">
.discover-page{
  padding-bottom: 250rpx;
  background-color: #2D3134;
  .notice-bar{
    padding-left: 26rpx;
  }

  .main-content{
    padding: 20rpx 32rpx;
    .hot-topic{
      .title{
        margin-bottom: 20rpx;
        font-weight: 600;
        font-size: 36rpx;
        line-height: 50rpx;
      }

      .topic-list{
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 72rpx;
        grid-gap: 20rpx;
        grid-auto-rows: auto;
        padding: 18rpx 26rpx;
        border-radius: 10px;
        background-color: #3A3E41;
        .topic-item{
          display: flex;
          .image{
            width: 72rpx;
            height: 72rpx;
            border-radius: 10rpx;
            margin-right: 20rpx;
          }

          .label{
            overflow: hidden;
            text-overflow: ellipsis;
            display:-webkit-box; //作为弹性伸缩盒子模型显示。
            -webkit-box-orient:vertical; //设置伸缩盒子的子元素排列方式--从上到下垂直排列
            -webkit-line-clamp:2; //显示的行
          }
        }
      }
    }

    .popular-goods,
    .all-like,
    .recent{
      margin: 20rpx 0;
      .title-row{
        display: flex;
        align-items: center;
        margin-bottom: 20rpx;
        .title{
          margin-right: auto;
          font-weight: 600;
          font-size: 36rpx;
          line-height: 50rpx;
        }

        .icon-wrapper{
          display: flex;
          align-items: center;
          font-weight: 600;
          font-size: 20rpx;
          line-height: 28rpx;
          color: #888888;
          .icon{
            margin-left: 20rpx;
          }
        }
      }

      .goods-list,
      .all-like-list{
        margin: 0 auto;
        display: grid;
        grid-auto-flow: column;
        gap: 20rpx;
        overflow-y: hidden;
        overscroll-behavior-x: contain;
        scroll-snap-type: x mandatory;
        &::-webkit-scrollbar{
          /* 隐藏滚动条 */
          display: none;
        }
        .goods-item,
        .all-like-item{
          scroll-snap-align: center;
          background-color: #3A3E41;
          .image{
            max-width: none;
            object-fit: contain;
            border-radius: 20rpx;
          }

          .label{
            font-weight: 600;
            font-size: 24rpx;
            line-height: 34rpx;
            margin: 26rpx;
            width: 240rpx;
            overflow: hidden;
            white-space: nowrap;
            text-overflow: ellipsis;
          }
        }

        .all-like-item{
          display: grid;
          grid-template-columns: 280rpx 280rpx;
          grid-template-rows: 270rpx;
          font-weight: 600;
          font-size: 32rpx;
          line-height: 45rpx;
          background-color: #252726;
          border-radius: 20rpx;
          .info{
            display: flex;
            flex-direction: column;
            padding: 35rpx 26rpx;
            .desc{
              font-size: 24rpx;
              line-height: 34rpx;
              margin-top: 15rpx;
              margin-bottom: auto;
            }

            .avatar-wrapper{
              .image{
                width: 42rpx;
                height: 42rpx;
                border-radius: 50%;
                margin-right: 10rpx;
                vertical-align: bottom;
              }

              .nickname{
                font-weight: 400;
                font-size: 24rpx;
                line-height: 42rpx;
              }
            }
          }

          .image{
            flex: 1;
            border-radius: 20rpx;
          }
        }
      }
    }

    .recent-item{
      padding: 22rpx 26rpx;
      background-color: #252726;
      .avatar-wrapper{
        display: flex;
        .image{
          width: 82rpx;
          height: 82rpx;
          border-radius: 50%;
          margin-right: 27rpx;
        }

        .detail{
          .nick-name{
            font-weight: 600;
            font-size: 32rpx;
            line-height: 45rpx;
            color: #F2E1BD;
          }

          .time{
            font-weight: 600;
            font-size: 24rpx;
            line-height: 34rpx;
            color: #888888;
          }
        }
      }

      .content{
        //font-weight: 600;
        font-size: 32rpx;
        line-height: 45rpx;
        margin: 37rpx 0 65rpx 0;
        overflow: hidden;
        text-overflow: ellipsis;
        display:-webkit-box; //作为弹性伸缩盒子模型显示。
        -webkit-box-orient:vertical; //设置伸缩盒子的子元素排列方式--从上到下垂直排列
        -webkit-line-clamp:4; //显示的行
      }

      .image-list{
        display: grid;
        grid-template-columns: repeat(3,1fr);
        grid-template-rows: auto;
        gap:20rpx;
      }

      .icon-wrapper{
        display: flex;
        justify-content: center;
        align-items: center;
        margin-top: 40rpx;
        .comment,
        .thumb-up{
          display: flex;
          justify-content: center;
          align-items: center;
          flex: 1;
          color: #888888;
          .icon{
            margin-right: 16rpx;
          }
        }
        .comment{
          border-right:1rpx solid #D9D9D9;
        }
      }
    }

    .release{
      position: fixed;
      display: grid;
      place-items: center;
      right: 58rpx;
      bottom: 135rpx;
      width: 88rpx;
      height: 88rpx;
      border-radius: 50%;
      background-color: #F3E1BD;
    }
  }
}
</style>
