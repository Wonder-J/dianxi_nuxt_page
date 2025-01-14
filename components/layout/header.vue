<template>
  <div class="header">
    <div class="mainWeb">
      <a class="logo" href="/"></a>
      <div class="tabGroup">
        <a
          class="tab"
          :class="route.path === item.url ? 'tab-active' : ''"
          v-for="(item, key) in tabList"
          :key="key"
          :href="item.url"
        >
          {{ item.label }}
        </a>
      </div>
      <div class="rightBar">
        <i class="icon"></i>
        <span>0574-6399-8369</span>
      </div>
    </div>
  </div>
</template>
<script lang="ts" setup>
const route = useRoute();

const tabList = reactive([
  {
    url: "/solution",
    label: "解决方案",
  },
  {
    url: "/product",
    label: "产品服务",
  },
  {
    url: "/example",
    label: "典型案例",
  },
  {
    url: "/news",
    label: "新闻动态",
  },
  {
    url: "/about",
    label: "关于点溪",
  },
]);
</script>
<style lang="scss" scoped>
.header {
  width: 100%;
  background: #fff;
  .mainWeb {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding-top: 30px;
    .logo {
      width: 248px;
      height: 39px;
      background: url("/image/logo.png") no-repeat;
      font-weight: 400;
      background-size: contain;
    }
    .tabGroup {
      width: 600px;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      .tab {
        font-size: 20px;
        color: #000;
        line-height: 40px;
        cursor: pointer;
        padding-bottom: 30px;
        text-decoration: none;
      }
      .tab-active {
        border-bottom: 3px solid #258ffb;
        color: #1d86ff;
      }
    }
    .rightBar {
      width: 210px;
      height: 40px;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      .icon {
        width: 35px;
        height: 35px;
        background: url("/image/tell.png") no-repeat;
        background-size: contain;
        margin-top: 1.5px;
      }
      span {
        font-size: 20px;
        color: #3e92ae;
        line-height: 40px;
      }
    }
  }
}
</style>
<style lang="scss">
.mainWeb {
  margin: 0 auto;
  width: 1200px;
  height: auto;
  font-family: "OPPOSans";
}
</style>
