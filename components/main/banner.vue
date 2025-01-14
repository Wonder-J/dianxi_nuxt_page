<template>
  <div class="banner">
    <swiper
      :pagination="{ clickable: true }"
      autoplay
      :slides-per-view="1"
      :modules="modules"
    >
      <swiper-slide><img src="/image/banner.png" alt="" /></swiper-slide>
      <swiper-slide><img src="/image/banner.png" alt="" /></swiper-slide>
      <swiper-slide><img src="/image/banner.png" alt="" /></swiper-slide>
    </swiper>
  </div>
</template>

<script lang="ts">
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination } from "swiper/modules";
import "swiper/css";
import "swiper/css/pagination";
import { defineComponent } from "vue";

export default defineComponent({
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Pagination],
    };
  },
});
</script>

<style lang="scss">
.banner {
  width: 100%;
  height: 650px;
  .swiper-container {
    img {
      width: 100%;
      height: 650px;
    }
  }
  .swiper-pagination {
    left: -300px;
    bottom: 100px;
    .swiper-pagination-bullet {
      width: 64px;
      height: 9px;
      border-radius: 5px;
    }
  }
}
</style>
<style lang="scss">
.banner {
  /* 这里可以添加一些自定义样式 */
  .swiper-pagination-bullet {
    width: 64px;
    height: 9px;
    border-radius: 5px;
    background: rgba(255, 255, 255, 0.5);
    opacity: 1;
    box-shadow: 2px 3px 4px 1px rgba(0, 0, 0, 0.1);
  }
  .swiper-pagination-bullet-active {
    background: rgba(255, 255, 255, 1);
  }
}
</style>
