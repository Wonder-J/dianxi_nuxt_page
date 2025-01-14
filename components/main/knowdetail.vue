<template>
  <div class="knowdetail">
    <div class="knowdetail-main">
      <!-- 左边内容 -->
      <div class="left-container">
        <div class="left-container-title">{{ knowData.title }}</div>
        <div class="left-container-content">
          {{ knowData.content }}
        </div>
        <div class="left-container-list">
          <div
            class="left-container-list-item"
            v-for="(item, index) in knowData.knowList"
            :key="index"
          >
            <img :src="item.iconUrl" alt="" class="left-container-list-icon" />
            <div>{{ item.title }}</div>
          </div>
        </div>
        <div class="detail-button">
          <img
            class="detail-button-img"
            src="/image/knowDetailButton.png"
            alt=""
          />
        </div>
      </div>
      <!-- 右边内容 -->
      <div class="right-container">
        <div class="right-container-content">
          <div
            v-for="(item, index) in knowData.advantages"
            :key="index"
            class="right-container-content-item"
          >
            <div>
              <img :src="item.iconUrl" alt="" />
            </div>
            <div class="right-container-content-item-title">
              {{ item.title }}
            </div>
            <div class="right-container-content-item-content">
              {{ item.content }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "index",
  data() {
    return {
      knowData: {
        title: "专业补充“源-网-口”的服务企业",
        content: "完善排水体系端的建设、运营和管理一体化",
        knowList: [
          {
            title: "智能设备全地形收集",
            iconUrl: "/image/iconSetting.png",
          },
          {
            title: "设备实时数据采集传输",
            iconUrl: "/image/iconDiscount.png",
          },
          {
            title: "根据天气切换模式",
            iconUrl: "/image/iconMoreCircle.png",
          },
          {
            title: "统一平台设备管理",
            iconUrl: "/image/iconEditSquare.png",
          },
        ],
        advantages: [
          {
            iconUrl: "/image/iconDoubleWindow.png",
            title: "收得进",
            content: "污水源头能够有效地被收集进入污水收集系统",
          },
          {
            iconUrl: "/image/iconDoubleWindow.png",
            title: "分的清",
            content:
              "污水在收集的过程中能被清晰的分类，根据不同分类调整输送模式",
          },
          {
            iconUrl: "/image/iconClickCircle.png",
            title: "送得出",
            content: "污水再收集后能够被顺利输送至污水处理厂进行处理",
          },
          {
            iconUrl: "/image/iconDefend.png",
            title: "管得住",
            content: "污水收集系统的运行和管理进行有效的监管和控制",
          },
        ],
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.knowdetail {
  font-family: OPPOSans;
  height: 650px;
  background: url("/image/knowdetailBackground.png") no-repeat;
  background-size: cover;
  &-main {
    display: flex;
    justify-content: space-between;
    width: 1200px;
    height: 100%;
    margin: 0 auto;
    .left-container {
      height: 100%;
      display: flex;
      flex-direction: column;
      justify-content: center;
      width: 50%;
      &-title {
        background: linear-gradient(223.39deg, #5fc5d3 16.25%, #3383fa 83.18%);
        background-clip: text;
        font-size: 24px;
        margin-bottom: 18px;
        -webkit-text-fill-color: transparent;
      }
      &-content {
        font-size: 48px;
        color: #ffffff;
        margin-bottom: 35px;
      }
      &-list {
        display: flex;
        flex-wrap: wrap;
        &-item {
          display: flex;
          width: 45%;
          font-size: 20px;
          color: #ffffff;
          margin-bottom: 20px;
        }
        &-icon {
          width: 30px;
        }
      }
      .detail-button {
        margin-top: 24px;
        &-img {
          cursor: pointer;
        }
      }
    }
    .right-container {
      display: flex;
      align-items: center;
      width: 50%;
      height: 100%;
      &-content {
        display: flex;
        flex-wrap: wrap;
        width: 100%;
        justify-content: flex-end;
        &-item {
          border-radius: 10px;
          margin-right: 18px;
          margin-bottom: 18px;
          width: 32%;
          height: 246px;
          display: flex;
          flex-direction: column;
          justify-content: center;
          padding: 0 45px;
          background: linear-gradient(
            65.01deg,
            rgba(127, 148, 194, 0.3) 0.98%,
            rgba(78, 142, 187, 0.4) 57.41%,
            rgba(8, 96, 168, 0.5) 99.12%
          );
          &-title {
            color: #fcfcfc;
            font-size: 24px;
          }
          &-content {
            color: #ffffff99;
          }
        }
        &-item:nth-child(even) {
          margin-right: 0px;
        }
      }
    }
  }
}
</style>
