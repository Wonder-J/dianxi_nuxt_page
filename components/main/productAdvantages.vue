<template>
  <div class="advantages">
    <div class="advantages-main">
      <div class="advantages-main-title">{{ advantagesDatas.title }}</div>
      <div class="advantages-main-content">
        {{ advantagesDatas.content }}
      </div>
      <div class="advantages-main-cards">
        <div class="advantages-main-cards-first">
          <div class="first-card-text-container">
            <div class="first-card-text-container-text">
              <div class="first-card-text-container-text-title">
                {{ advantagesDatas.firstCard.title }}
              </div>
              <div class="first-card-text-container-text-desc">
                {{ advantagesDatas.firstCard.desc }}
              </div>
            </div>
            <div class="first-card-text-container-topicon">
              <img
                class="first-card-text-container-topicon-img"
                :src="advantagesDatas.firstCard.topIconUrl"
                alt=""
              />
            </div>
          </div>
          <div class="advantages-main-cards-first-item-menus">
            <template
              :key="item.title"
              v-for="(item, index) in advantagesDatas.firstCard.menus"
            >
              <div class="first-item-menu-item">
                <div class="first-item-menu-item-icon">
                  <img :src="item.iconUrl" alt="" />
                </div>
                <div class="first-item-menu-item-title">
                  {{ item.title }}
                </div>
              </div>
              <div
                :key="item.iconUrl"
                v-if="index !== advantagesDatas.firstCard.menus.length - 1"
                class="first-item-menu-dividing"
              ></div>
            </template>
          </div>
        </div>
        <div
          class="normal-card"
          :key="index"
          v-for="(normalCardItem, index) in advantagesDatas.normalCards"
        >
          <div class="normal-card-topicon">
            <img :src="normalCardItem.topIconUrl" alt="" />
          </div>
          <div class="normal-card-text-container">
            <div class="normal-card-text-container-title">
              {{ normalCardItem.title }}
            </div>
            <div class="normal-card-text-container-subtitle">
              {{ normalCardItem.subtitle }}
            </div>
            <div
              class="normal-card-text-container-desc"
              :key="normalDesc"
              v-for="normalDesc in normalCardItem.descArr"
            >
              {{ normalDesc }}
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
      advantagesDatas: {
        title: "产品优势",
        content: "多年技术服务，运行有保障，技术更放心",
        firstCard: {
          title: "闭环产品",
          desc: "从方案到落地，从软件到硬件，满足您的全流程服务",
          topIconUrl: "/images/shopping.png",
          menus: [
            {
              title: "方案设计",
              iconUrl: "/image/todo.png",
            },
            {
              title: "软件开发",
              iconUrl: "/image/documentOut.png",
            },
            {
              title: "硬件部署",
              iconUrl: "/image/printf.png",
            },
            {
              title: "服务落地",
              iconUrl: "/image/material.png",
            },
          ],
          topIconUrl: "/image/shopping.png",
        },
        normalCards: [
          {
            title: "02",
            subtitle: "安全稳定",
            descArr: ["获得ISO安全认证", "保障您的数据安全"],
            topIconUrl: "/image/phone.png",
          },
          {
            title: "03",
            subtitle: "极速响应",
            descArr: ["全天候实时监控", "智能设备自动预警"],
            topIconUrl: "/image/dataDiscuss.png",
          },
        ],
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.advantages {
  font-family: OPPOSans;
  height: 650px;
  background: url("/image/productAdvantagesBackground.png") no-repeat;
  background-size: cover;
  &-main {
    width: 1200px;
    height: 100%;
    margin: 0 auto;
    &-title {
      font-size: 48px;
      font-weight: 400;
      color: #000000;
      padding-top: 96px;
    }
    &-content {
      font-size: 20px;
      font-weight: 400;
      color: #000000;
    }
    &-cards {
      display: flex;
      justify-content: space-between;
      &-first {
        box-shadow: 0px 5px 20px 0px #80b1c640;
        flex: 2;
        background: linear-gradient(
          257.89deg,
          rgba(255, 255, 255, 0.1) 0.51%,
          #ffffff 100%
        );
        border-radius: 10px;
        margin-top: 43px;
        .first-card-text-container {
          display: flex;
          &-text {
            padding: 65px 0 0 49px;
            &-title {
              font-size: 32px;
              color: #000000;
              font-weight: 400;
            }
            &-desc {
              font-size: 16px;
              color: #000000;
              font-weight: 400;
            }
          }
          &-topicon {
            margin-right: 5px;
          }
        }

        &-item-menus {
          display: flex;
          margin-top: 74px;
          justify-content: space-between;
          margin: 70px 60px 44px 60px;
          .first-item-menu {
            &-item {
              &-icon {
                display: flex;
                justify-content: center;
              }
              &-title {
                color: #000000;
                font-weight: 400;
                font-size: 16px;
              }
            }
            &-dividing {
              border: 1px solid #e1e8f1;
              width: 1px;
            }
          }
        }
      }
      .normal-card {
        box-shadow: 0px 5px 20px 0px #80b1c640;
        border-radius: 10px;
        flex: 1;
        margin: 43px 0 0 20px;
        background: linear-gradient(
          257.89deg,
          rgba(255, 255, 255, 0.1) 0.51%,
          #ffffff 100%
        );
        &-topicon {
          display: flex;
          justify-content: flex-end;
        }
        &-text-container {
          margin-left: 44px;
          &-title {
            font-size: 32px;
            font-weight: 400;
            color: #b3d4f2;
          }
          &-subtitle {
            font-size: 24px;
            font-weight: 400;
            color: #000000;
            margin-bottom: 20px;
          }
          &-desc {
            font-size: 16px;
            font-weight: 400;
            line-height: 20px;
            color: #000000;
            margin-bottom: 5px;
          }
        }
      }
    }
  }
}
</style>
