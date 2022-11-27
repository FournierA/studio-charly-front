<template>
  <div class="charly-service-highlight">
    <div class="charly-service-hightlight__content container">
      <h2 class="charly-service-highlight__title">{{ title }}</h2>

      <p class="charly-service-highlight__description" v-html="description"></p>
    </div>

    <swiper
      class="charly-service-highlight__slider"
      :modules="modules"
      :slides-per-view="3"
      :space-between="50"
      :loop="true"
      :lazy="true"
      navigation
      :pagination="{ clickable: true }"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
    >
      <swiper-slide
        v-for="(portrait, index) in portraits"
        :key="index"
        class="charly-service-highlight__slider__image"
      >
        <img :src="portrait" />
      </swiper-slide>
    </swiper>
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
  computed: {
    portraits() {
      const images = this.importAll(
        require.context("../assets/portraits/", false, /\.(png|jpe?g|svg)$/)
      );

      return images;
    },
  },
  methods: {
    importAll(r) {
      return r.keys().map(r);
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
  background-color: rgb(285, 188, 176);
  padding: 33px 0 44px 0;
  width: 100%;

  &__title {
    text-align: center;
    margin: 0;
  }

  &__description {
    padding: 0 32px;
    text-align: center;
  }

  &__slider {
    padding: 64px 0;

    ::v-deep {
      .swiper-wrapper {
        margin-left: -17.1%;
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
      }
    }
  }
}
</style>
