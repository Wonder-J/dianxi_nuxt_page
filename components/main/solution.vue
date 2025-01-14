<template>
  <div class="solution">
    <div class="mainWeb">
      <div class="header">
        <div class="title">解决方案</div>
        <div class="decs">深耕细分场景，提供更加垂直的行业解决方案</div>
      </div>
      <div class="body">
        <div class="left">
          <div
            @mouseover="changeTab(key)"
            :class="index == key ? 'tab active' : 'tab'"
            :key="key"
            v-for="(item, key) in solutionList"
          >
            <span class="sort">0{{ key + 1 }}</span
            ><span class="text">{{ item.tab }}</span>
          </div>
        </div>
        <div class="right">
          <div class="header">
            <span class="num">0{{ index + 1 }}</span>
            <span class="title">{{ solutionList[index].title }}</span>
          </div>
          <div class="content">
            <div class="decsList">
              <div
                class="decs"
                v-for="(decs, decKey) in solutionList[index].decsList"
                :key="decKey"
              >
                <i
                  class="icon"
                  :style="{
                    background: `url('${decs.icon}')`,
                    backgroundSize: 'cover',
                  }"
                ></i>
                <span class="title">{{ decs.title }}</span>
              </div>
            </div>
            <div class="imgList">
              <swiper
                direction="vertical"
                :pagination="{ clickable: true }"
                class="swiper"
                :modules="modules"
                :slides-per-view="1"
              >
                <swiper-slide
                  class="swiper-slide"
                  v-for="(img, imgKey) in solutionList[index].imgList"
                  :key="imgKey"
                  ><img :src="img.url" alt=""
                /></swiper-slide>
              </swiper>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { defineComponent } from "vue";
import { Pagination } from "swiper/modules";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/pagination";

export default defineComponent({
  name: "Solution",
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Pagination],
    };
  },
  data() {
    return {
      index: 0,
      solutionList: [
        {
          tab: "农污治理",
          title: "投资1111万元，达到污水收集率99.9%",
          decsList: [
            {
              icon: "/image/iconActivity.png",
              title: "完善基础设施",
            },
            {
              icon: "/image/iconScan.png",
              title: "提升排口管治",
            },
            {
              icon: "/image/iconDocument.png",
              title: "数智提效降本",
            },
            {
              icon: "/image/iconWarning.png",
              title: "预防洪涝灾害",
            },
          ],
          imgList: [
            {
              url: "image/banner.png",
            },
            {
              url: "image/banner.png",
            },
            {
              url: "image/banner.png",
            },
            {
              url: "image/banner.png",
            },
          ],
        },
        {
          tab: "水质提升",
          title: "投资2222万元，达到污水收集率99.9%",
          decsList: [
            {
              icon: "/image/iconActivity.png",
              title: "完善基础设施",
            },
            {
              icon: "/image/iconScan.png",
              title: "提升排口管治",
            },
            {
              icon: "/image/iconDocument.png",
              title: "数智提效降本",
            },
            {
              icon: "/image/iconWarning.png",
              title: "预防洪涝灾害",
            },
          ],
          imgList: [
            {
              url: "/image/banner.png",
            },
            {
              url: "/image/banner.png",
            },
            {
              url: "/image/banner.png",
            },
            {
              url: "/image/banner.png",
            },
          ],
        },
        {
          tab: "排口整治",
          title: "投资3333万元，达到污水收集率99.9%",
          decsList: [
            {
              icon: "/image/iconActivity.png",
              title: "完善基础设施",
            },
            {
              icon: "/image/iconScan.png",
              title: "提升排口管治",
            },
            {
              icon: "/image/iconDocument.png",
              title: "数智提效降本",
            },
            {
              icon: "/image/iconWarning.png",
              title: "预防洪涝灾害",
            },
          ],
          imgList: [
            {
              url: "/image/banner.png",
            },
            {
              url: "/image/banner.png",
            },
            {
              url: "/image/banner.png",
            },
            {
              url: "/image/banner.png",
            },
          ],
        },
        {
          tab: "智控改造",
          title: "投资4444万元，达到污水收集率99.9%",
          decsList: [
            {
              icon: "/image/iconActivity.png",
              title: "完善基础设施",
            },
            {
              icon: "/image/iconScan.png",
              title: "提升排口管治",
            },
            {
              icon: "/image/iconDocument.png",
              title: "数智提效降本",
            },
            {
              icon: "/image/iconWarning.png",
              title: "预防洪涝灾害",
            },
          ],
          imgList: [
            {
              url: "/image/banner.png",
            },
            {
              url: "/image/banner.png",
            },
            {
              url: "/image/banner.png",
            },
            {
              url: "/image/banner.png",
            },
          ],
        },
      ],
    };
  },
  mounted() {},
  methods: {
    changeTab(key: number) {
      this.index = key;
    },
  },
});
</script>
<style lang="scss" scoped>
.solution {
  width: 100%;
  height: 650px;
  background: url("/image/solution.png") no-repeat;
  background-size: cover;
  padding: 94px 0;
  box-sizing: border-box;
  .mainWeb {
    .header {
      display: flex;
      flex-direction: column;
      .title {
        font-size: 48px;
        font-weight: 400;
        color: #000;
      }
      .decs {
        font-size: 20px;
        font-weight: 400;
        color: #000;
      }
    }
    .body {
      margin-top: 34px;
      height: 340px;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      .left {
        width: 285px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        .tab {
          color: #000;
          // line-height: 24px;
          font-size: 20px;
          font-weight: 400;
          width: 285px;
          height: 65px;
          border-radius: 10px;
          cursor: pointer;
          background: #fff;
          text-align: center;
          line-height: 65px;
          .sort {
            color: #abcee5;
            font-size: 24px;
            font-weight: 400;
            // line-height: 24px;
            margin-right: 12px;
          }
        }
        .active {
          background: url("/image/solutionTabBg.png") no-repeat;
          background-size: cover;
          .text {
            /* 使用linear-gradient创建一个渐变背景 */
            background-image: linear-gradient(45deg, #64ccce, #2f7dfe);
            /* 背景不重复 */
            background-size: 100%;
            /* 文字颜色 */
            color: transparent;
            /* 让背景填充文字 */
            background-clip: text;
            /* 确保兼容性 */
            -webkit-background-clip: text;
            /* 文字不可见 */
            -webkit-text-fill-color: transparent;
            /* 避免文字下方的空白 */
            display: inline-block;
          }
          .sort {
            display: none;
          }
        }
      }
      .right {
        width: 860px;
        .header {
          display: flex;
          flex-direction: row;
          border-bottom: 1px solid #c5dbe8;
          .num {
            font-size: 36px;
            font-weight: 600;
            margin-right: 14px;
            background-image: linear-gradient(45deg, #64ccce, #2f7dfe);
            /* 背景不重复 */
            background-size: 100%;
            /* 文字颜色 */
            color: transparent;
            /* 让背景填充文字 */
            background-clip: text;
            /* 确保兼容性 */
            -webkit-background-clip: text;
            /* 文字不可见 */
            -webkit-text-fill-color: transparent;
            /* 避免文字下方的空白 */
            display: inline-block;
            border-bottom: 5px solid #22adff;
          }
          .title {
            font-size: 24px;
            color: #000;
            font-weight: 400;
            line-height: 60px;
          }
        }
        .content {
          margin-top: 32px;
          width: 100%;
          height: 240px;
          display: flex;
          flex-direction: row;
          justify-content: space-between;
          .decsList {
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: flex-start;
            .decs {
              display: flex;
              flex-direction: row;
              justify-content: space-between;
              .icon {
                display: block;
                width: 24px;
                height: 24px;
                background: #000;
              }
              .title {
                margin-left: 8px;
                font-size: 20px;
                font-weight: 400;
                line-height: 24px;
                color: #000;
              }
            }
          }
          .imgList {
            overflow: hidden;
            height: 240px;
            border-radius: 10px;
            .swiper {
              height: 100%;
              width: 100%;

              .swiper-slide {
                display: flex;
                justify-content: center;
                align-items: center;
                text-align: center;
                font-weight: bold;
              }
              .swiper-pagination :deep(.swiper-pagination-bullet) {
                box-shadow: 0px 4px 4px 0px #0000000d;
                height: 6px;
              }
            }
            img {
              width: 570px;
              height: 240px;
            }
          }
        }
      }
    }
    /* 渐变动画关键帧 */
    @keyframes gradient-text {
      0% {
        background-position: 0% 50%;
      }
      50% {
        background-position: 100% 50%;
      }
      100% {
        background-position: 0% 50%;
      }
    }
  }
}
</style>

<style lang="scss">
.solution {
  .swiper-pagination-bullet {
    box-shadow: 0px 4px 4px 0px #0000000d;
    width: 6px;
    height: 30px;
    border-radius: 5px;
  }
  .swiper-pagination-bullet-active {
    background: #ffffff;
  }
}
</style>
