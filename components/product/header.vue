<template>
  <div class="product-header">
    <div class="header-title-container">
      <div class="header-title">产品服务</div>
      <div class="header-desc">
        从源头到终端，从产品到服务，点溪为您全程守护
      </div>
    </div>
    <div class="product-tabs">
      <div class="front-page">
        <img src="/productImg/frontPage.png" alt="" />
      </div>
      <div
        class="product-item-tab"
        :key="tabIndex"
        v-for="(tabItem, tabIndex) in tabsData"
        @click="changeIndex(tabIndex)"
      >
        {{ tabItem.title }}
      </div>
    </div>
    <div class="product-tabs-content">
      <div class="left-content">
        <div class="left-title">
          <span class="title">构建</span>
          <span class="blue-title">"1+N+X"</span>
          <span class="title">产品服务体系</span>
        </div>
        <div class="left-desc">
          <div
            class="left-item"
            :key="contentIndex"
            v-for="(contentItem, contentIndex) in tabsData[tabIndex].content"
          >
            <div class="left-left">
              <div>
                <img :src="contentItem.iconUrl" alt="" />
              </div>
              <span class="left-blue-title">{{ contentItem.numTitle }}</span>
              <span class="unit">{{ contentItem.unit }}</span>
            </div>
            <div class="desc">
              <div class="left-desc-title">{{ contentItem.descTitle }}</div>
              <div class="left-desc-content">
                {{ contentItem.descContent }}
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="right-content">
        <img src="/productImg/dynamicBg.png" alt="" />
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
const tabIndex = ref(0);

const changeIndex = (index: number) => {
  tabIndex.value = index;
};

const tabsData = reactive([
  {
    title: "污水收集",
    content: [
      {
        iconUrl: "/productImg/statistics.png",
        numTitle: "1",
        unit: "个",
        descTitle: "管理平台",
        descContent:
          "点溪提供一个集中式的管理平台，用于监控、控制和优化所有连接的智能设备和应用场景",
      },
      {
        iconUrl: "/productImg/cube.png",
        numTitle: "N",
        unit: "台",
        descTitle: "智能设备",
        descContent:
          "多台部署在不同地点的智能设备，智能排口处理装置、智能管网监测装置、智能输送能力提升装置等，它们通过物联网技术与中央管理平台相连",
      },
      {
        iconUrl: "/productImg/addCube.png",
        numTitle: "X",
        unit: "个",
        descTitle: "应用场景",
        descContent:
          "多个定制化的应用场景，城市内涝防治、农村污水治理、河道生态修复等，每个场景都通过智能设备和平台进行管理",
      },
    ],
  },
  {
    title: "智能监测",
    content: [
      {
        iconUrl: "/productImg/statistics.png",
        numTitle: "1",
        unit: "个",
        descTitle: "管理平台",
        descContent:
          "点溪提供一个集中式的管理平台，用于监控、控制和优化所有连接的智能设备和应用场景",
      },
      {
        iconUrl: "/productImg/cube.png",
        numTitle: "N",
        unit: "台",
        descTitle: "智能设备",
        descContent:
          "多台部署在不同地点的智能设备，智能排口处理装置、智能管网监测装置、智能输送能力提升装置等，它们通过物联网技术与中央管理平台相连",
      },
      {
        iconUrl: "/productImg/addCube.png",
        numTitle: "X",
        unit: "个",
        descTitle: "应用场景",
        descContent:
          "多个定制化的应用场景，城市内涝防治、农村污水治理、河道生态修复等，每个场景都通过智能设备和平台进行管理",
      },
    ],
  },
  {
    title: "数智改造",
    content: [
      {
        iconUrl: "/productImg/statistics.png",
        numTitle: "1",
        unit: "个",
        descTitle: "管理平台",
        descContent:
          "点溪提供一个集中式的管理平台，用于监控、控制和优化所有连接的智能设备和应用场景",
      },
      {
        iconUrl: "/productImg/cube.png",
        numTitle: "N",
        unit: "台",
        descTitle: "智能设备",
        descContent:
          "多台部署在不同地点的智能设备，智能排口处理装置、智能管网监测装置、智能输送能力提升装置等，它们通过物联网技术与中央管理平台相连",
      },
      {
        iconUrl: "/productImg/addCube.png",
        numTitle: "X",
        unit: "个",
        descTitle: "应用场景",
        descContent:
          "多个定制化的应用场景，城市内涝防治、农村污水治理、河道生态修复等，每个场景都通过智能设备和平台进行管理",
      },
    ],
  },
  {
    title: "平台集成",
    content: [
      {
        iconUrl: "/productImg/statistics.png",
        numTitle: "1",
        unit: "个",
        descTitle: "管理平台",
        descContent:
          "点溪提供一个集中式的管理平台，用于监控、控制和优化所有连接的智能设备和应用场景",
      },
      {
        iconUrl: "/productImg/cube.png",
        numTitle: "N",
        unit: "台",
        descTitle: "智能设备",
        descContent:
          "多台部署在不同地点的智能设备，智能排口处理装置、智能管网监测装置、智能输送能力提升装置等，它们通过物联网技术与中央管理平台相连",
      },
      {
        iconUrl: "/productImg/addCube.png",
        numTitle: "X",
        unit: "个",
        descTitle: "应用场景",
        descContent:
          "多个定制化的应用场景，城市内涝防治、农村污水治理、河道生态修复等，每个场景都通过智能设备和平台进行管理",
      },
    ],
  },
]);
</script>

<style lang="scss" scoped>
.product-header {
  .header-title-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 300px;
    background: url("/productImg/productHeaderBg.png") no-repeat;
    background-size: cover;
    .header-title {
      color: #000;
      font-size: 64px;
    }
    .header-desc {
      color: rgba(0, 0, 0, 0.8);
      font-size: 24px;
    }
  }
  .product-tabs {
    height: 45px;
    display: flex;
    background-color: #fff;
    margin-left: 18%;
    .front-page {
      background-color: #64ccce;
      height: 100%;
      width: 50px;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
    }
    .product-item-tab {
      display: flex;
      align-items: center;
      margin-left: 86px;
    }
  }
  .product-tabs-content {
    height: 800px;
    background: url("/productImg/buildBg.png") no-repeat;
    background-size: cover;
    display: flex;
    justify-content: flex-end;
    .left-content {
      padding-top: 58px;
      .left-title {
        margin-bottom: 30px;
        .title {
          color: #000;
          font-size: 48px;
        }
        .blue-title {
          background: linear-gradient(223deg, #5fc5d3 16.25%, #3383fa 83.18%);
          font-size: 48px;
          background-clip: text;
          -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
        }
      }
      .left-desc {
        .left-item {
          display: flex;
          align-items: center;
          margin-bottom: 30px;
          .left-left {
            display: flex;
            width: 160px;
            .left-blue-title {
              background: linear-gradient(180deg, #469fea 0%, #5dc2d5 100%);
              font-size: 48px;
              background-clip: text;
              -webkit-background-clip: text;
              -webkit-text-fill-color: transparent;
              display: flex;
              align-items: center;
            }
            .unit {
              color: #000;
              font-size: 20px;
              display: flex;
              box-sizing: content-box;
              align-items: center;
              position: relative;
              bottom: -10px;
            }
          }
          .desc {
            position: relative;
            top: 70px;
            padding-left: 24px;
            .left-desc-title {
              color: #000;
              font-size: 24px;
              margin-bottom: 20px;
            }
            .left-desc-content {
              font-size: 20px;
              font-weight: 400;
              max-width: 400px;
            }
          }
        }
      }
    }
  }
}
</style>
