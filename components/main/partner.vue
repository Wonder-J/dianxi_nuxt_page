<template>
  <div>
    <div class="partner">
      <div class="partner-text-container">
        <div class="partner-text-container-title">
          {{ partnerData.title }}
        </div>
        <div class="partner-text-container-desc">
          {{ partnerData.desc }}
        </div>
      </div>
      <CustomAutoSliderSwiper>
        <swiper-slide
          :key="index"
          v-for="(sliderItem, index) in partnerData.sliderPartners1"
        >
          <img :src="`/image/${sliderItem.logoUrl}`" alt="" />
        </swiper-slide>
      </CustomAutoSliderSwiper>
      <CustomAutoSliderSwiper :offset="500" :speed="1500">
        <swiper-slide
          :key="index"
          v-for="(sliderItem1, index) in partnerData.sliderPartners2"
        >
          <img :src="sliderItem1.logoUrl" alt="" />
        </swiper-slide>
      </CustomAutoSliderSwiper>
    </div>
    <div class="dynamic-news">
      <div class="dynamic-news-text-container">
        <div class="news-title">新闻动态</div>
        <div class="news-more">更多咨询 ></div>
      </div>
      <div class="news-card-cotainer">
        <div
          class="normal-container"
          :key="news.backgroundUrl"
          v-for="news in partnerData.newsData"
        >
          <div class="normal-container-top">
            <div class="normal-container-top-title">
              <div class="whole-title">{{ news.topTitle }}</div>
            </div>
            <img :src="`/image/${news.backgroundUrl}`" alt="" />
          </div>
          <div class="content-container">
            <div class="content-container-title">{{ news.title }}</div>
            <div class="content-container-desc">{{ news.desc }}</div>
            <div class="content-container-time">{{ news.time }}</div>
          </div>
        </div>
        <div class="summary-container">
          <div class="summary-tabs">
            <div
              class="summary-tab"
              :key="summaryTabIndex"
              :class="
                tabIndex === summaryTabIndex ? 'news-tab-active' : 'news-tab'
              "
              v-for="(summaryTab, summaryTabIndex) in partnerData.otherNewsData"
              @mouseover="changeTab(summaryTabIndex)"
            >
              {{ summaryTab.title }}
            </div>
          </div>
          <div class="summary-content-container">
            <div
              class="summary-content-item"
              :key="contentIndex"
              v-for="(contentItem, contentIndex) in partnerData.otherNewsData[
                tabIndex
              ].content"
            >
              <div class="summary-content-item-title">
                {{ contentItem.title }}
              </div>
              <div class="summary-content-item-time">
                {{ contentItem.time }}
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { SwiperSlide } from "swiper/vue";
import { ref } from "vue";
const tabIndex = ref(0);

const changeTab = (index) => {
  tabIndex.value = index;
};

const partnerData = ref({
  title: "合作伙伴",
  desc: "口碑铸造影响力，已有多家政府、高校和企业与点溪环保合作",
  sliderPartners1: [
    {
      logoUrl: "beijinguniversity.png",
    },
    {
      logoUrl: "beijinguniversity.png",
    },
    {
      logoUrl: "beijinguniversity.png",
    },
    {
      logoUrl: "beijinguniversity.png",
    },
    {
      logoUrl: "beijinguniversity.png",
    },
    {
      logoUrl: "beijinguniversity.png",
    },
    {
      logoUrl: "beijinguniversity.png",
    },
    {
      logoUrl: "beijinguniversity.png",
    },
  ],
  sliderPartners2: [
    {
      logoUrl: "/image/beijinguniversity1.png",
    },
    {
      logoUrl: "/image/beijinguniversity1.png",
    },
    {
      logoUrl: "/image/beijinguniversity1.png",
    },
    {
      logoUrl: "/image/beijinguniversity1.png",
    },
    {
      logoUrl: "/image/beijinguniversity1.png",
    },
    {
      logoUrl: "/image/beijinguniversity1.png",
    },
    {
      logoUrl: "/image/beijinguniversity1.png",
    },
    {
      logoUrl: "/image/beijinguniversity1.png",
    },
  ],
  newsData: [
    {
      topTitle: "企业资讯",
      title: "宁波市大数据局朱晓丽局长带队莅临点溪调研",
      desc: "朱晓丽局长充分肯定点溪环保各项工作所取得的成绩，表示在数字化改革的大背景下，要驰而不息、行而不缀的推进水环境治理工作。",
      time: "2023-02-21",
      backgroundUrl: "news1.png",
    },
    {
      topTitle: "媒体报道",
      title: "《慈溪日报》重点报道！",
      desc: "2023年2月3日，慈溪日报首版对点溪环保做了重点报道——《点溪首创全域“污水零直排”智慧微治版》。",
      time: "2023-02-17",
      backgroundUrl: "news1.png",
    },
  ],
  otherNewsData: [
    {
      title: "企业资讯",
      content: [
        {
          title: "慈溪市政协主席陈杰峰一行莅临点溪环保调研1",
          time: "2023-02-17",
        },
        {
          title: "点溪环保电子河长公示牌正式公布亮相！",
          time: "2023-01-10",
        },
        {
          title: "点溪环保“机器人”智能治水尽显身手",
          time: "2023-01-10",
        },
        {
          title: "点溪智能排口收集处理装置筑牢防汛抗台安全防线",
          time: "2023-01-10",
        },
      ],
    },
    {
      title: "媒体报道",
      content: [
        {
          title: "慈溪市政协主席陈杰峰一行莅临点溪环保调研2",
          time: "2023-02-17",
        },
        {
          title: "点溪环保电子河长公示牌正式公布亮相！",
          time: "2023-01-10",
        },
        {
          title: "点溪环保“机器人”智能治水尽显身手",
          time: "2023-01-10",
        },
        {
          title: "点溪智能排口收集处理装置筑牢防汛抗台安全防线",
          time: "2023-01-10",
        },
      ],
    },
    {
      title: "点溪动态",
      content: [
        {
          title: "慈溪市政协主席陈杰峰一行莅临点溪环保调研3",
          time: "2023-02-17",
        },
        {
          title: "点溪环保电子河长公示牌正式公布亮相！",
          time: "2023-01-10",
        },
        {
          title: "点溪环保“机器人”智能治水尽显身手",
          time: "2023-01-10",
        },
        {
          title: "点溪智能排口收集处理装置筑牢防汛抗台安全防线",
          time: "2023-01-10",
        },
      ],
    },
  ],
});
</script>

<style lang="scss" scoped>
.partner {
  &-text-container {
    width: 1200px;
    height: 100%;
    margin: 0 auto;
    padding-top: 73px;
    &-title {
      font-size: 48px;
      font-weight: 400;
      color: #000000;
    }
    &-desc {
      font-size: 20px;
      font-weight: 400;
      color: #000000;
    }
  }
}

.dynamic-news {
  padding-bottom: 50px;
  width: 1200px;
  height: 100%;
  margin: 0 auto;
  &-text-container {
    display: flex;
    justify-content: space-between;
    .news-title {
      font-family: OPPOSans;
      font-size: 48px;
      font-weight: 400;
      color: #000000;
      margin-top: 50px;
      line-height: 48px;
      margin-bottom: 18px;
    }
    .news-more {
      font-family: OPPOSans;
      font-size: 20px;
      font-weight: 400;
      color: #00000080;
      display: flex;
      align-items: center;
    }
  }
  .news-card-cotainer {
    display: flex;
    .normal-container {
      box-shadow: 0px 4px 10px 0px #b6cbea;
      flex: 1;
      margin-right: 20px;
      border-radius: 10px;
      display: flex;
      flex-direction: column;
      &-top {
        position: relative;
        flex: 1;
        img {
          width: 100%;
          height: 230px;
        }
        &-title {
          position: absolute;
          bottom: 0;
          padding: 5px 15px;
          background-color: #fff;
          border-radius: 10px 10px 0 0;
          .whole-title {
            background: linear-gradient(
              223.39deg,
              #5fc5d3 16.25%,
              #3383fa 83.18%
            );
            background-clip: text;
            -webkit-text-fill-color: transparent;
            font-family: OPPOSans;
            font-size: 16px;
            font-weight: 400;
          }
        }
      }

      .content-container {
        padding: 24px;
        flex: 1;
        display: flex;
        flex-direction: column;
        &-title {
          color: #000000;
          font-family: OPPOSans;
          font-size: 20px;
          font-weight: 400;
          margin-bottom: 25px;
        }
        &-desc {
          font-family: OPPOSans;
          font-size: 16px;
          font-weight: 400;
          color: #00000080;
          margin-bottom: 16px;
          flex: 1;
        }
        &-time {
          display: flex;
          justify-content: flex-end;
          margin-right: 5px;
        }
      }
    }
    .summary-container {
      box-shadow: 0px 4px 10px 0px #b6cbea;
      flex: 1;
      padding: 28px;
      display: flex;
      border-radius: 10px;
      flex-direction: column;
      .summary-tabs {
        display: flex;
        justify-content: space-between;
        margin-bottom: 20px;
        .summary-tab {
          padding: 7px 12px;
          border-radius: 5px;
          border: 1px solid #00000080;
          font-size: 20px;
          font-weight: 400;
          cursor: pointer;
        }
      }
    }
    .summary-content-container {
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      .summary-content-item {
        .summary-content-item-title {
          color: #000000;
          font-size: 20px;
          font-weight: 400;
          margin-right: 30px;
        }
        .summary-content-item-time {
          color: #00000080;
          font-size: 14px;
          font-weight: 400;
          display: flex;
          justify-content: flex-end;
        }
      }
    }
  }
}

.news-tab-active {
  font-family: OPPOSans;
  background: linear-gradient(223.39deg, #5fc5d3 16.25%, #3383fa 83.18%);
  color: #fff;
  font-size: 20px;
  font-weight: 400;
  border: none !important;
}
.news-tab {
  font-family: OPPOSans;
  font-size: 20px;
  font-weight: 400;
}
</style>

<style lang="scss">
// 使图片预览可以平滑滚动，这里不能使用scoped，否则不能覆盖组件外的CSS
.supplier-swiper {
  .swiper-container-free-mode {
    .swiper-wrapper {
      -webkit-transition-timing-function: linear !important;
      -moz-transition-timing-function: linear !important;
      -ms-transition-timing-function: linear !important;
      -o-transition-timing-function: linear !important;
      transition-timing-function: linear !important;
      margin: 0 auto !important;
    }
  }
}
</style>
