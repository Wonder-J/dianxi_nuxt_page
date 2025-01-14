<template>
  <div class="lifeCycle">
    <div class="mainWeb">
      <div class="tabGroup">
        <div
          class="tab"
          v-for="(item, key) in tabList"
          :key="key"
          :style="{
            background: `url(/image/lifeCycleTab${key + 1}.png)`,
            backgroundSize: 'Cover',
          }"
        ></div>
      </div>
      <div class="info">
        <div class="box" v-for="(item, key) in infoList" :key="key">
          <div class="unit">
            <span class="num">{{ item.num }}</span
            >{{ item.unit }}
          </div>
          <div class="title">{{ item.title }}</div>
        </div>
      </div>
      <div class="content"></div>
    </div>
  </div>
</template>
<script>
export default {
  name: "index",
  components: {},
  data() {
    return {
      infoList: [
        {
          num: 2000,
          title: "上线设备数量",
          unit: "台+",
        },
        {
          num: 888,
          title: "采集监测数据",
          unit: "万+",
        },
        {
          num: 888,
          title: "服务用户数",
          unit: "人+",
        },
        {
          num: 111,
          title: "涵盖城市数",
          unit: "个",
        },
      ],
      tabList: [
        {
          link: "/",
        },
        {
          link: "/",
        },
        {
          link: "/",
        },
        {
          link: "/",
        },
      ],
    };
  },
  mounted() {},
  methods: {},
};
</script>
<style lang="scss" scoped></style>
<style lang="scss">
.lifeCycle {
  padding-top: 100px;
  box-sizing: border-box;
  width: 100%;
  height: 1300px;
  background: url("/image/lifeCycle.png") no-repeat;
  background-size: cover;
  .mainWeb {
    position: relative;
    .tabGroup {
      width: 100%;
      position: absolute;
      left: 0;
      top: -140px;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      z-index: 3;
      .tab {
        height: 80px;
        width: 284px;
        border-radius: 10px;
        cursor: pointer;
      }
      .tab:nth-of-type(1):hover {
        width: 298px;
        height: 128px;
        background: url("/image/lifeCycleTabHover1.png") !important;
        background-size: contain !important;
        transform: translateY(-48px);
      }
      .tab:nth-of-type(2):hover {
        width: 298px;
        height: 128px;
        background: url("/image/lifeCycleTabHover2.png") !important;
        background-size: contain !important;
        transform: translateY(-48px);
      }
      .tab:nth-of-type(3):hover {
        width: 298px;
        height: 128px;
        background: url("/image/lifeCycleTabHover3.png") !important;
        background-size: contain !important;
        transform: translateY(-48px);
      }
      .tab:nth-of-type(4):hover {
        width: 298px;
        height: 128px;
        background: url("/image/lifeCycleTabHover4.png") !important;
        background-size: contain !important;
        transform: translateY(-48px);
      }
    }
    .info {
      width: 100%;
      display: flex;
      flex-direction: row;
      justify-content: space-around;
      .box {
        .unit {
          font-size: 24px;
          color: #000;
          font-weight: 400;
          .num {
            font-size: 40px;
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
        .title {
          font-size: 24px;
          color: #000;
          font-weight: 400;
        }
      }
    }
    .content {
      position: absolute;
      top: 136px;
      left: 0;
      width: 1223px;
      height: 990px;
      background: url("/image/lifeCycleContent.png") no-repeat;
      background-size: contain;
    }
  }
}
</style>
