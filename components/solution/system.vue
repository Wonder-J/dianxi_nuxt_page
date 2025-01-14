<template>
  <div class="system">
    <div class="background"></div>
    <div class="top-container">
      <div class="top-title">简单四步，快速搭建污水智慧收集系统</div>
      <div class="top-desc">构建”源-网-厂-口-河“排水设施全要素监管</div>
    </div>
    <div class="icon-desc-container">
      <div
        class="icon-desc-item"
        v-for="(iconItem, iconIndex) in iconDesc"
        :key="iconIndex"
      >
        <div class="icon-whole">
          <div class="icon">
            <div class="icon-circle">
              <img :src="iconItem.icon" alt="" />
            </div>
          </div>
          <div class="icon-title-container">
            <span class="icon-number">{{ `0${iconIndex + 1}` }}</span>
            <span class="icon-title">{{ iconItem.title }}</span>
          </div>
          <div class="icon-desc">{{ iconItem.desc }}</div>
        </div>
        <div class="icon-arrow" v-if="iconIndex !== iconDesc.length - 1">
          <img src="/solutionImg/arrow.png" alt="" />
        </div>
      </div>
    </div>
    <div class="system-img">
      <img src="/solutionImg/systemBg.png" alt="" />
    </div>
  </div>
</template>

<script lang="ts" setup>
const iconDesc = reactive([
  {
    icon: "/solutionImg/canLook.png",
    title: "可视",
    desc: "透明管理，一目了然，让污水管理尽在掌控",
  },
  {
    icon: "/solutionImg/canSearch.png",
    title: "可查",
    desc: "信息一手掌握，决策更精准，为您提供全面的数据查询支持",
  },
  {
    icon: "/solutionImg/canManage.png",
    title: "可管",
    desc: "线上调控，轻松应对，让运维处理更高效、更可靠",
  },
  {
    icon: "/solutionImg/canCompute.png",
    title: "可算",
    desc: "成本优化效益提升，以数据驱动实现污水处理的效益最大化",
  },
]);
</script>

<style lang="scss" scoped>
.system {
  position: relative;
  .background {
    background: linear-gradient(0deg, rgba(69, 188, 226, 0) 30%, #c3e0fe 100%);
    opacity: 0.3;
    position: absolute;
    width: 100%;
    height: 400px;
  }
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
  .icon-desc-container {
    display: flex;
    justify-content: center;
    margin-bottom: 15px;
    .icon-desc-item:last-child {
      max-width: 15%;
    }
    .icon-desc-item {
      display: flex;
      margin-right: 20px;
      max-width: 20%;
      .icon-whole {
        .icon {
          margin-bottom: 40px;
          .icon-circle {
            width: 100px;
            height: 100px;
            background: linear-gradient(180deg, #edf3ff 0%, #3a83fc 100%);
            border-radius: 50%;
            position: relative;
            img {
              top: -10px;
              right: -5px;
              position: absolute;
            }
          }
        }
        .icon-title-container {
          margin-bottom: 15px;
          .icon-number {
            font-size: 24px;
            background: linear-gradient(223deg, #5fc5d3 16.25%, #3383fa 83.18%);
            background-clip: text;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            display: inline-block;
            margin-right: 20px;
          }
          .icon-title {
            color: #000;
            font-size: 24px;
            font-style: normal;
            font-weight: 400;
            display: inline-block;
          }
        }
        .icon-desc {
          color: #000;
          font-size: 20px;
          font-style: normal;
          font-weight: 400;
        }
      }
      .icon-arrow {
        display: flex;
        align-items: center;
      }
    }
  }
  .system-img {
    img {
      width: 100%;
    }
  }
}
</style>
