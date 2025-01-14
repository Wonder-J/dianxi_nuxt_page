<template>
  <div class="benify">
    <div class="top-container">
      <div class="top-title">从收集到管理的全方位解决方案</div>
      <div class="top-desc">污水治理的智能革新</div>
    </div>
    <div class="benify-tabs">
      <div
        class="benify-tab"
        v-for="(itemTab, itemIndex) in tabsData"
        :key="itemIndex"
        @mouseenter="changeTab(itemIndex)"
      >
        <img :src="itemTab.iconUrl" alt="" />
        <div
          class="tab-title"
          :class="{
            'tab-title-active': itemIndex === activeIndex,
          }"
        >
          {{ itemTab.title }}
        </div>
        <div
          class="vector"
          :style="{
            opacity: itemIndex === activeIndex ? 1 : 0,
          }"
        >
          <img src="/solutionImg/tabVector.png" alt="" />
        </div>
      </div>
    </div>
    <div class="benify-tabs-content">
      <div class="content">
        <div class="tabs-content-title">{{ tabsData[activeIndex].title }}</div>
        <div class="tabs-content-detail">
          <div class="tabs-content-list">
            <div class="list-little-dividing"></div>
            <div class="list-dividing"></div>
            <div class="list-points-container">
              <div
                class="point"
                :key="itemIndex"
                v-for="(itemPoint, itemIndex) in tabsData[activeIndex].bfList"
              >
                <div class="point-img-container">
                  <img src="/solutionImg/tick.png" alt="" />
                </div>
                <div class="point-text-container">
                  <div class="point-title">{{ itemPoint.title }}</div>
                  <div class="point-desc">{{ itemPoint.desc }}</div>
                </div>
              </div>
            </div>
          </div>
          <div class="tabs-content-swiper">
            <swiper
              direction="vertical"
              :pagination="{ clickable: true }"
              class="swiper"
              :modules="[Pagination]"
              :slides-per-view="1"
            >
              <swiper-slide
                class="swiper-slide"
                v-for="(img, imgKey) in tabsData[activeIndex].imgList"
                :key="imgKey"
                ><img :src="img.url" alt=""
              /></swiper-slide>
            </swiper>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination } from "swiper/modules";
import "swiper/css";
import "swiper/css/pagination";

const activeIndex = ref(0);

const tabsData = reactive([
  {
    iconUrl: "/solutionImg/waterTank.png",
    title: "收得进",
    imgList: [
      {
        url: "/solutionImg/test.png",
      },
      {
        url: "/solutionImg/test.png",
      },
      {
        url: "/solutionImg/test.png",
      },
    ],
    bfList: [
      {
        title: "散点收集",
        desc: "针对偏远、复杂或小规模的污水源，通过污水管统一收集到设备内",
      },
      {
        title: "集中收集",
        desc: "将多个散点污水汇集至设备统一输送",
      },
      {
        title: "大流量收集",
        desc: "应对高峰、负荷的污水排放，通过高效运行的泵送技术，确保收集",
      },
    ],
  },
  {
    iconUrl: "/solutionImg/waterProvider.png",
    title: "分得清",
    imgList: [
      {
        url: "/solutionImg/test.png",
      },
      {
        url: "/solutionImg/test.png",
      },
      {
        url: "/solutionImg/test.png",
      },
      {
        url: "/solutionImg/test.png",
      },
    ],
    bfList: [
      {
        title: "散点收集",
        desc: "针对偏远、复杂或小规模的污水源，通过污水管统一收集到设备内",
      },
      {
        title: "集中收集",
        desc: "将多个散点污水汇集至设备统一输送",
      },
      {
        title: "大流量收集",
        desc: "应对高峰、负荷的污水排放，通过高效运行的泵送技术，确保收集",
      },
    ],
  },
  {
    iconUrl: "/solutionImg/gisPipe.png",
    title: "送得出",
    imgList: [
      {
        url: "/solutionImg/test.png",
      },
      {
        url: "/solutionImg/test.png",
      },
    ],
    bfList: [
      {
        title: "散点收集",
        desc: "针对偏远、复杂或小规模的污水源，通过污水管统一收集到设备内",
      },
      {
        title: "集中收集",
        desc: "将多个散点污水汇集至设备统一输送",
      },
      {
        title: "大流量收集",
        desc: "应对高峰、负荷的污水排放，通过高效运行的泵送技术，确保收集",
      },
    ],
  },
  {
    iconUrl: "/solutionImg/console.png",
    title: "管得住",
    imgList: [
      {
        url: "/solutionImg/test.png",
      },
    ],
    bfList: [
      {
        title: "散点收集",
        desc: "针对偏远、复杂或小规模的污水源，通过污水管统一收集到设备内",
      },
      {
        title: "集中收集",
        desc: "将多个散点污水汇集至设备统一输送",
      },
      {
        title: "大流量收集",
        desc: "应对高峰、负荷的污水排放，通过高效运行的泵送技术，确保收集",
      },
    ],
  },
]);

const changeTab = (index: number) => {
  activeIndex.value = index;
};
</script>

<style lang="scss" scoped>
$content-width: 75%;
.benify {
  .top-container {
    margin-bottom: 35px;
    padding-top: 65px;
    .top-title {
      font-size: 48px;
      font-weight: 400;
      color: #000000;
      display: flex;
      justify-content: center;
    }
    .top-desc {
      font-size: 24px;
      font-weight: 400;
      color: #000000;
      display: flex;
      justify-content: center;
    }
  }
  .benify-tabs {
    display: flex;
    justify-content: space-between;
    width: $content-width;
    margin: 0 auto;
    .benify-tab {
      display: flex;
      flex-direction: column;
      align-items: center;
      img {
        margin-bottom: 5px;
      }
      .tab-title {
        color: #000;
        font-size: 24px;
        font-weight: 400;
      }
      .tab-title-active {
        color: #30a0ff;
        font-size: 24px;
        font-weight: 400;
      }
      .vector {
        margin-right: 20px;
      }
    }
  }
  .benify-tabs-content {
    height: 540px;
    background: #e7f5ff;
    display: flex;
    justify-content: center;
    .content {
      width: $content-width;
      padding-top: 32px;
    }

    .tabs-content-title {
      background: linear-gradient(223deg, #5fc5d3 16.25%, #3383fa 83.18%);
      background-clip: text;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      font-size: 32px;
      margin-bottom: 26px;
    }
    .tabs-content-detail {
      display: flex;
      .tabs-content-list {
        flex: 1;
        .list-little-dividing {
          background: linear-gradient(180deg, #45bce2 0%, #65d0d1 100%);
          height: 3px;
          width: 10%;
        }
        .list-dividing {
          background-color: #abc5e8;
          height: 1px;
          width: 100%;
        }
        .list-points-container {
          margin-top: 45px;
          .point {
            display: flex;
            margin-bottom: 27px;
            .point-img-container {
              line-height: 24px;
              display: inline-block;
              padding-top: 3px;
              margin-right: 5px;
            }
            .point-text-container {
              .point-title {
                color: #000;
                font-size: 24px;
              }
            }
          }
        }
      }
      .tabs-content-swiper {
        flex: 2;
        height: 380px;
        .swiper :deep(.swiper-pagination-bullets) {
          top: 0 !important;
          transform: translate3d(0, 0, 0);
        }
        .swiper :deep(.swiper-pagination-bullet) {
          box-shadow: 0px 4px 4px 0px #0000000d;
          width: 10px;
          height: 50px;
          border-radius: 5px;
        }
        .swiper :deep(.swiper-pagination-bullet-active) {
          background: #b1d3ff !important;
        }

        .swiper {
          height: 100%;
          width: 100%;

          .swiper-slide {
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            font-weight: bold;
            border-radius: 10px;
          }
        }
      }
    }
  }
}
</style>
