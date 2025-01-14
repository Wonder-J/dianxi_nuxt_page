<template>
  <div class="ache">
    <div class="top-background">
      <img src="/solutionImg/smartWater.png" alt="" />
      <div class="background-divding"></div>
    </div>
    <div class="industry-ache">
      <div class="industry-top">
        <div class="industry-top-title">行业通点</div>
        <div class="industry-top-desc">您的痛点我们都知道</div>
      </div>
      <div class="industry-card-container">
        <div
          class="first-card"
          :style="{
            background: `url(${firstAcheCardData.backgroundUrl})`,
            backgroundSize: 'cover',
            backgroundRepeat: 'no-repeat',
            backgroundPosition: 'center',
          }"
        >
          <div class="first-card-container">
            <div class="first-card-title">{{ firstAcheCardData.title }}</div>
            <div
              class="first-card-item"
              :key="cardItem.iconUrl"
              v-for="cardItem in firstAcheCardData.acheList"
            >
              <div class="first-row">
                <div class="first-row-icon">
                  <img :src="cardItem.iconUrl" alt="" />
                </div>
                <div class="first-row-indextitle">{{ cardItem.index }}</div>
              </div>
              <div class="second-row">
                <div class="second-row-title">{{ cardItem.title }}</div>
                <div class="second-row-desc">{{ cardItem.desc }}</div>
              </div>
            </div>
          </div>
        </div>
        <div
          class="normal-card"
          :key="acheItem.backgroundUrl"
          :style="{
            background: `url(${acheItem.backgroundUrl})`,
            backgroundSize: 'Cover',
          }"
          v-for="acheItem in normalAcheCardData"
        >
          <div class="normal-card-title">{{ acheItem.title }}</div>
          <div
            class="normal-card-desc"
            :key="itemDesc"
            v-for="itemDesc in acheItem.desc"
          >
            {{ itemDesc }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.ache {
  .top-background {
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      vertical-align: bottom;
    }
    .background-divding {
      height: 10px;
      background-color: #4e5675;
    }
  }
  .industry-ache {
    height: 650px;
    background: url("/image/solution.png") no-repeat;
    .industry-top {
      padding: 30px;
      .industry-top-title {
        display: flex;
        color: #000000;
        font-size: 48px;
        justify-content: center;
      }
      .industry-top-desc {
        display: flex;
        justify-content: center;
        color: #000000;
        font-size: 24px;
      }
    }
    .industry-card-container {
      display: flex;
      justify-content: center;
      margin: 0 auto;
      width: 70%;
      .first-card {
        flex: 3;
        height: 430px;
        border-radius: 10px;
        padding: 54px 0 0 30px;
        .first-card-container {
          .first-card-title {
            color: #000000;
            font-size: 24px;
            margin-bottom: 40px;
          }
          .first-card-item {
            display: flex;
            margin-bottom: 30px;
            .first-row {
              display: flex;
              .first-row-indextitle {
                font-size: 20px;
                background: linear-gradient(
                  98.43deg,
                  #53a7a9 0%,
                  #43a2c0 96.77%
                );
                background-clip: text;
                -webkit-text-fill-color: transparent;
                line-height: 31px;
              }
            }
            .second-row {
              margin-left: 7px;
              .second-row-title {
                font-size: 20px;
                line-height: 31px;
                color: #000000;
              }
              .second-row-desc {
                color: #00000080;
                margin-top: 6px;
                font-size: 16px;
              }
            }
          }
        }
      }
      .normal-card {
        flex: 1;
        height: 430px;
        border-radius: 10px;
        margin-right: 15px;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        padding-bottom: 45px;
        padding-left: 25px;
        .normal-card-title {
          color: #fff;
          font-size: 24px;
          margin-bottom: 20px;
        }
        .normal-card-desc {
          color: #fff;
          font-size: 16px;
        }
        .normal-card-desc:not(:last-child) {
          margin-bottom: 8px;
        }
      }
    }
  }
}
</style>

<script lang="ts" setup>
const firstAcheCardData = reactive({
  title: "收集难",
  backgroundUrl: "/solutionImg/firstAche.png",
  acheList: [
    {
      iconUrl: "/solutionImg/iconClose.png",
      index: "痛点一",
      title: "污水收集管网不完善，收集率低",
      desc: "资金投入不足、城市快速发展导致现有设施跟不上需求",
    },
    {
      iconUrl: "/solutionImg/iconNotification.png",
      index: "痛点二",
      title: "管网老旧破损和混接错接",
      desc: "长期损耗缺乏维护，设计跟不上技术",
    },
    {
      iconUrl: "/solutionImg/iconPassword.png",
      index: "痛点三",
      title: "数据资源分散，整合度低",
      desc: "缺乏统一的数据标准和集成平台，形成数据孤岛",
    },
  ],
});

const normalAcheCardData = reactive([
  {
    title: "监管难",
    desc: ["智能化手段缺失", "过程难以规范监管"],
    backgroundUrl: "/solutionImg/secondAche.png",
  },
  {
    title: "施工难",
    desc: ["居住密度低", "工期长工况复杂"],
    backgroundUrl: "/solutionImg/thirdAche.png",
  },
  {
    title: "监管难",
    desc: ["政府投资压力大", "资金来源方式单一"],
    backgroundUrl: "/solutionImg/forthAche.png",
  },
]);
</script>
