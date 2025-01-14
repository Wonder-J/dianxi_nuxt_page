<template>
  <div class="ability">
    <div class="hardware">
      <div class="hardware-title">硬件尽显不俗实力</div>
      <div class="hardware-tabs">
        <div
          class="hardware-tab"
          :class="{
            'hardware-tab-active': hardwareIndex === curHardwareIndex,
          }"
          v-for="(hardwareItem, hardwareIndex) in hardwareDatas"
          :key="hardwareIndex"
          @mouseenter="changeHardwareIndex(hardwareIndex)"
        >
          {{ hardwareItem.title }}
        </div>
      </div>
      <div class="hardware-img-list">
        <div
          class="hardware-img"
          :key="imgIndex"
          v-for="(imgItem, imgIndex) in hardwareDatas[curHardwareIndex].imgList"
        >
          <img :src="imgItem.imgUrl" alt="" />
        </div>
      </div>
    </div>
    <div class="software">
      <div class="software-text-container">
        <div class="software-text">软件为您解决管理</div>
        <div class="software-list-container">
          <div
            class="software-list-item"
            :key="bfIndex"
            v-for="(benfifyItem, bfIndex) in softwareBenfify"
          >
            <div class="software-benfify-icon">
              <img :src="benfifyItem.iconUrl" alt="" />
            </div>
            <div class="software-benfify-text">
              <div class="software-benfify-title">{{ benfifyItem.title }}</div>
              <div class="software-benfify-desc">{{ benfifyItem.desc }}</div>
            </div>
          </div>
        </div>
      </div>
      <div class="software-imgbg">
        <img src="/productImg/softwareBg.png" alt="" />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
const curHardwareIndex = ref(0);

const changeHardwareIndex = (index: number) => {
  curHardwareIndex.value = index;
};

const hardwareDatas = reactive([
  {
    title: "污水收集类",
    imgList: [
      {
        imgUrl: "/productImg/test.png",
      },
      {
        imgUrl: "/productImg/test.png",
      },
      {
        imgUrl: "/productImg/test.png",
      },
      {
        imgUrl: "/productImg/test.png",
      },
      {
        imgUrl: "/productImg/test.png",
      },
    ],
  },
  {
    title: "智能监测类",
    imgList: [
      {
        imgUrl: "/productImg/test.png",
      },
    ],
  },
  {
    title: "数智改造类",
    imgList: [
      {
        imgUrl: "/productImg/test.png",
      },
    ],
  },
]);

const softwareBenfify = reactive([
  {
    title: "基础功能我们为您解决",
    desc: "提供基础功能，数据采集、设备控制、实时监控等",
    iconUrl: "/productImg/graph.png",
  },
  {
    title: "分散数据我们为您集成",
    desc: "实现多系统协同，整合资源，提升效率",
    iconUrl: "/productImg/chart.png",
  },
  {
    title: "复杂数据我们为您分析",
    desc: "深入数据分析，优化决策，驱动创新",
    iconUrl: "/productImg/setting.png",
  },
]);
</script>

<style lang="scss" scoped>
.ability {
  .hardware {
    padding-left: 18%;
    padding-top: 70px;
    height: 650px;
    background-color: #eff3f7;
    .hardware-title {
      color: #000;
      font-size: 48px;
      margin-bottom: 15px;
    }
    .hardware-tabs {
      display: flex;
      border-bottom: 1px solid #e1e8f1;
      width: 1200px;
      .hardware-tab {
        color: rgba(0, 0, 0, 0.5);
        font-size: 24px;
        margin-right: 55px;
        cursor: pointer;
      }
      .hardware-tab-active {
        color: #2f7dfe;
        padding-bottom: 5px;
        font-size: 24px;
        border-bottom: 3px solid #2f7dfe;
      }
    }
    .hardware-img-list {
      display: flex;
      justify-content: space-between;
      margin-right: 10%;
      margin-top: 20px;
      .hardware-img {
        width: 250px;
        height: 380px;
      }
    }
  }
  .software {
    padding-left: 18%;
    height: 650px;
    margin-top: 85px;
    display: flex;
    .software-text-container {
      margin-right: 115px;
      .software-text {
        color: #000;
        font-size: 48px;
        margin-bottom: 42px;
      }
      .software-list-container {
        .software-list-item {
          display: flex;
          margin-bottom: 50px;
          .software-benfify-icon {
            padding-top: 3px;
            margin-right: 25px;
          }
          .software-benfify-text {
            .software-benfify-title {
              color: #000;
              font-size: 24px;
              margin-bottom: 16px;
            }
            .software-benfify-desc {
              color: #000;
              font-size: 20px;
            }
          }
        }
      }
    }
  }
}
</style>
