<template>
  <div class="auto-slider-swiper" ref="container">
    <swiper
      :modules="modules"
      :slides-per-view="slidesPerView"
      :loop="true"
      :autoplay="autoplay"
      :speed="speed"
      :offset="offset"
      @swiper="onSwiper"
      @mouseenter="onMouseEnter"
      @mouseleave="onMouseLeave"
    >
      <slot></slot>
    </swiper>
  </div>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { ref, onMounted, computed } from "vue";
import { Autoplay } from "swiper/modules";
import "swiper/css";

const props = defineProps({
  speed: {
    type: Number,
    default: 3000,
  },
  offset: {
    type: Number,
    default: 50,
  },
});

const container = ref(null);
const swiperInstance = ref(null);

const modules = [Autoplay];

const autoplay = ref({
  delay: 0,
  disableOnInteraction: false,
});

// 计算每个slide的宽度（包括间距）
const slideWidth = 320; // 300px 宽度 + 20px 间距

// 计算应显示的slide数量
const slidesPerView = computed(() => {
  if (!container.value) return 1;
  const containerWidth = container.value.offsetWidth;
  return Math.floor(containerWidth / slideWidth);
});

const onSwiper = (swiper) => {
  swiperInstance.value = swiper;
};

const onMouseEnter = () => {
  if (swiperInstance.value) {
    swiperInstance.value.autoplay.stop();
  }
};

const onMouseLeave = () => {
  if (swiperInstance.value) {
    swiperInstance.value.autoplay.start();
  }
};

onMounted(() => {
  window.addEventListener("resize", () => {
    if (swiperInstance.value) {
      swiperInstance.value.update();
    }
  });
});
</script>

<style lang="scss">
.auto-slider-swiper {
  width: 100%;
  .swiper {
    height: 153px;
    width: 100%;
    margin-top: 30px;
    .swiper-slide {
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      font-weight: bold;
      height: 150px;
      margin-top: 5px;
      border-radius: 10px;
    }
  }
}

:deep(.swiper-wrapper) {
  transition-timing-function: linear !important;
}

// 使图片预览可以平滑滚动，这里不能使用scoped，否则不能覆盖组件外的CSS
.auto-slider-swiper {
  .swiper-container-free-mode {
    .swiper-wrapper {
      transition-timing-function: linear !important;
      margin: 0 auto !important;
    }
  }
}
</style>
