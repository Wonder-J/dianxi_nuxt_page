<template>
  <div class="layout-bottom-container">
    <div class="layout-bottom">
      <div class="left-bottom">
        <div class="left-code">
          <img src="/bottomImg/dianxi.png" alt="" />
          <img src="/bottomImg/code.png" alt="" />
          <div class="code-desc">更多解决方案</div>
        </div>
        <div class="left-desc">
          <div class="left-desc-title">
            点溪环保，做您身边的排水体系的科技先行者
          </div>
          <div class="left-desc-connect">
            <div
              class="left-desc-connect-item"
              :key="connectItem.icon"
              v-for="connectItem in connectData"
            >
              <div class="connect-icon">
                <img :src="connectItem.icon" alt="" />
              </div>
              <div class="connect-tv">
                <div class="connect-title">{{ connectItem.title }}</div>
                <div class="connect-value">{{ connectItem.value }}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="right-bottom">
        <div
          class="right-item-tabs"
          :key="itemTabsIndex"
          v-for="(itemTabs, itemTabsIndex) in allTabs"
        >
          <div class="right-tab-title">{{ itemTabs.title }}</div>
          <div
            class="right-tab"
            :key="itemTabIndex"
            v-for="(itemTab, itemTabIndex) in itemTabs.tabList"
          >
            {{ itemTab.title }}
          </div>
        </div>
      </div>
    </div>
    <div class="copyright">
      <div class="dividing"></div>
      <div class="first-desc">
        版权所有：点溪环保 | 版本：2.0.0 | 开发者：宁波点溪环保科技有限公司
      </div>
      <div class="second-desc">ICP主体备案号：浙ICP备2021028263号-1</div>
      <div class="third-desc">Copyright © dxenv.com 2022 保留所有权利。</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.layout-bottom-container {
  background-color: #000;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  .layout-bottom {
    padding-top: 50px;
    display: flex;
    margin-bottom: 135px;
    .left-bottom {
      flex: 1;
      display: flex;
      margin-right: 130px;
      .left-code {
        img:first-of-type {
          margin-bottom: 43px;
        }

        img:nth-of-type(2) {
          margin-bottom: 10px;
        }

        display: flex;
        flex-direction: column;
        .code-desc {
          font-size: 20px;
          font-weight: 400;
          color: #ffffff;
          display: flex;
          justify-content: center;
        }
      }

      .left-desc {
        margin-left: 40px;
        .left-desc-title {
          font-size: 20px;
          font-weight: 400;
          color: #f9f9f9;
          margin-bottom: 40px;
        }
        .left-desc-connect {
          .left-desc-connect-item {
            display: flex;
            .connect-icon {
              margin-right: 20px;
            }
            .connect-tv {
              display: flex;
              flex-direction: column;
              justify-content: flex-start;
              margin-bottom: 45px;
              .connect-title {
                color: #ffffff99;
                font-size: 20px;
              }
              .connect-value {
                font-weight: 400;
                font-size: 24px;
                color: #fff;
              }
            }
          }
        }
      }
    }
    .right-bottom {
      flex: 1;
      display: flex;
      justify-content: space-between;
      .right-item-tabs {
        font-size: 20px;
        .right-tab-title {
          color: #fff;
          margin-bottom: 40px;
          display: flex;
          justify-content: center;
        }
        .right-tab {
          color: #ffffff99;
          margin-bottom: 18px;
          cursor: pointer;
        }
        .right-tab:hover {
          color: #fff;
          transition: all 0.3s ease-in-out;
        }
      }
    }
  }
  .copyright {
    width: 100%;
    display: flex;
    flex-direction: column;
    flex-wrap: wrap;
    .dividing {
      display: flex;
      border: 1px solid #ffffff33;
      margin: 0 255px;
      justify-content: center;
      margin-bottom: 10px;
    }
    .first-desc {
      display: flex;
      justify-content: center;
      font-size: 20px;
      color: #fff;
    }
    .second-desc {
      display: flex;
      justify-content: center;
      font-size: 14px;
      color: #fff;
      margin: 5px 0;
    }
    .third-desc {
      display: flex;
      justify-content: center;
      font-size: 14px;
      color: #fff;
    }
  }
}
</style>

<script lang="ts" setup>
const connectData = reactive([
  {
    icon: "/bottomImg/phone.png",
    title: "联系电话",
    value: "0574-63998369",
  },
  {
    icon: "/bottomImg/email.png",
    title: "邮箱",
    value: "dianxi@dxenv.com",
  },
  {
    icon: "/bottomImg/address.png",
    title: "地址",
    value: "浙江省慈溪市白沙路街道三北大街2588号环杭州湾智能产业园B幢14楼",
  },
]);

const allTabs = reactive([
  {
    title: "关于点溪",
    tabList: [
      {
        title: "公司简介",
      },
      {
        title: "发展历程",
      },
      {
        title: "企业文化",
      },
      {
        title: "荣誉资质",
      },
      {
        title: "专家风采",
      },
      {
        title: "加入我们",
      },
    ],
  },
  {
    title: "产品服务",
    tabList: [
      {
        title: "污水收集类",
      },
      {
        title: "智能监测类",
      },
      {
        title: "系统设计类",
      },
      {
        title: "数据分析类",
      },
    ],
  },
  {
    title: "合作支持",
    tabList: [
      {
        title: "帮助中心",
      },
      {
        title: "合作伙伴",
      },
      {
        title: "联系我们",
      },
      {
        title: "管理后台",
      },
    ],
  },
  {
    title: "友情链接",
    tabList: [
      {
        title: "雪迪龙",
      },
      {
        title: "江能企业",
      },
      {
        title: "理工环科",
      },
    ],
  },
]);
</script>
