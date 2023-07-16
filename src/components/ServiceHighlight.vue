<template>
  <div class="charly-service-highlight">
    <div class="charly-service-hightlight__content inner-container">
      <h2 class="charly-service-highlight__title">{{ title }}</h2>

      <p class="charly-service-highlight__description" v-html="description"></p>
    </div>

    <div class="charly-service-highlight__line"></div>

    <div class="charly-service-highlight__slider-container">
      <swiper
        class="charly-service-highlight__slider"
        :modules="modules"
        :slides-per-view="3"
        :space-between="23"
        :loop="true"
        :lazy="true"
        navigation
        :pagination="{ clickable: true }"
        @swiper="onSwiper"
        @slideChange="onSlideChange"
      >
        <swiper-slide
          v-for="(picture, index) in pictures"
          :key="index"
          class="charly-service-highlight__slider__image"
        >
          <img :src="picture" />
        </swiper-slide>
      </swiper>
    </div>
  </div>
</template>

<script>
import { Navigation, Pagination } from "swiper";

import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

export default {
  name: "ServiceHighlight",
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      default: null,
    },
    pictures: {
      type: Array,
      default: () => [],
    },
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      onSwiper,
      onSlideChange,
      modules: [Navigation, Pagination],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.charly-service-highlight {
  position: relative;
  background-color: rgb(285, 188, 176);
  padding: 45px 0;
  width: 100%;

  &__line {
    width: 1241px;
    position: absolute;
    height: 100%;
    top: 0;
    left: 50%;
    transform: translateX(-50%);

    &::before {
      content: "";
      display: block;
      width: 30px;
      height: 30px;
      background-color: transparent;
      box-shadow: inset 2px 2px 3px -1px #00000045;
      position: absolute;
      top: 80px;
      left: 0;
      border-top-left-radius: 100%;
      border-top: 2px solid #ce5334;
      border-left: 2px solid #ce5334;
    }

    &::after {
      content: "";
      display: block;
      width: 30px;
      height: 100%;
      background-color: transparent;
      box-shadow: inset 2px -2px 3px -1px #00000045;
      position: absolute;
      top: 112px;
      left: 0;
      border-left: 2px solid #ce5334;
    }
  }

  &__title {
    position: relative;
    text-align: left;
    margin: 0;
    text-transform: uppercase;

    &::before {
      content: "";
      display: block;
      width: 90px;
      height: 5px;
      background-color: transparent;
      box-shadow: inset -1px 2px 3px -1px #00000045;
      position: absolute;
      bottom: -14.5px;
      left: -19px;
      border-top: 2px solid #ce5334;
    }

    &::after {
      content: "";
      display: block;
      position: absolute;
      background: #ffbcb0;
      height: 10px;
      width: 2px;
      bottom: -16.5px;
      left: 69px;
    }
  }

  &__description {
    padding: 0 32px;
    text-align: left;
  }

  &__slider-container {
    position: relative;
  }

  &__slider {
    position: static;
    width: 1241px;
    margin: auto;
    padding: 64px 0;
    overflow: visible;

    ::v-deep {
      .swiper-wrapper {
        height: 577px;
        margin-left: -17.1%;
      }

      .swiper-slide {
        border: 15px solid white;
        box-shadow: 0px 3px 10px #00000066;
      }

      .swiper-button-prev,
      .swiper-button-next {
        width: 40px;
        height: 80px;
      }

      .swiper-button-prev::after,
      .swiper-button-next::after {
        content: "";
        display: block;
        width: 100%;
        height: 100%;
        background-position: 50% 50%;
        background-size: contain;
        background-repeat: no-repeat;
      }

      .swiper-button-prev::after {
        background-image: url("/src/assets/icons/left-chevron.svg");
      }

      .swiper-button-next::after {
        background-image: url("/src/assets/icons/right-chevron.svg");
      }

      .swiper-pagination-bullet {
        background: transparent;
        border: 1px solid grey;
        opacity: 1;
        width: 10px;
        height: 10px;

        &.swiper-pagination-bullet-active {
          background: #cd5334;
          border-color: #cd5334;
          box-shadow: 0px 1px 16px #555;
        }
      }
    }

    &__image {
      height: 100%;

      img {
        display: block;
        width: 100%;
        max-height: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
