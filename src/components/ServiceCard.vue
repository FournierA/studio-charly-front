<template>
  <div class="service-card" :class="variantClass">
    <div v-if="variant === 'notebook'" class="service-card__bullets"></div>

    <div class="service-card__header">
      <h2>
        <span class="underline">{{ title }}</span>
      </h2>
      <p v-html="description"></p>
    </div>

    <div class="service-card__image-container">
      <div
        v-for="(image, index) in images"
        :key="index"
        class="service-card__image-container__item"
      >
        <img :src="require(`@/assets/${image}`)" />
      </div>
    </div>
  </div>
</template>

<script>
export const ServiceCardVariant = {
  CARD: "card",
  CARD_MULTIPLE: "card-multiple",
  NOTEBOOK: "notebook",
};

export default {
  name: "ServiceCard",
  components: {},
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      default: null,
    },
    images: {
      type: Array,
      default: null,
    },
    variant: {
      type: String,
      default: ServiceCardVariant.CARD,
    },
  },
  computed: {
    variantClass() {
      return `service-card--${this.variant}`;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.service-card {
  &__image-container__item {
    width: 100%;
    height: 100%;
  }

  img {
    width: 100%;
    height: 100%;
    max-height: 100%;
    object-fit: cover;
    object-position: center;
  }
}

.service-card--card,
.service-card--card-multiple {
  background: #fff;
  border-top-left-radius: 12px;
  border-top-right-radius: 12px;
  box-shadow: 2px 2px 3px #00000047;
  padding-bottom: 89px;

  .service-card__header {
    display: grid;
    grid-template-columns: 300px auto;
    align-items: center;
    padding: 32px 64px;

    h2 {
      font-size: 50px;
      text-transform: uppercase;
    }
  }
}

.service-card--card {
  .service-card__image-container {
    position: relative;
    height: 574px;

    &::after {
      content: "";
      display: block;
      position: absolute;
      width: 435px;
      height: 3px;
      bottom: -12px;
      right: 13px;
      background-color: #ce5334;
    }

    img {
      width: 100%;
      max-height: 100%;
      object-fit: cover;
      object-position: center;
    }
  }
}

.service-card--card-multiple {
  .service-card__image-container {
    position: relative;
    height: 574px;
    padding: 0 64px;
    display: grid;
    grid-template-columns: calc(70% - 65px) 30%;
    gap: 65px;

    &::after {
      content: "";
      display: block;
      position: absolute;
      width: 435px;
      height: 3px;
      bottom: -12px;
      left: 16px;
      background-color: #e8b9ad;
    }
  }
}

.service-card--notebook {
  position: relative;
  display: grid;
  grid-template-columns: 40% 60%;

  .service-card__bullets {
    background-image: url("/src/assets/icons/notebook-bullets.svg");
    width: 14px;
    height: 100%;
    position: absolute;
    left: 13px;
    top: 0;
    background-position: 0px 13px;
  }

  &::before {
    content: "";
    display: block;
    width: 2px;
    height: 100%;
    background-color: #ce5334;
    box-shadow: 2px 2px 3px #00000045;
    position: absolute;
    top: 0;
    left: 0;
  }

  .service-card__header {
    grid-column: 2;
    grid-row: 1;
    display: flex;
    flex-direction: column;

    h2 {
      font-size: 30px;
      width: 400px;
      border-radius: 58px;
      padding: 30px 60px;
      background-color: #fff;
      box-shadow: inset 3px 3px 2px #00000045;

      .underline {
        width: calc(100%);
        background-image: linear-gradient(
          transparent calc(100% - 2px),
          #ce5334 2px
        );
        background-repeat: no-repeat;
        background-size: 100% 100%;
      }
    }

    p {
      background-color: #fff;
      box-shadow: inset 3px 3px 2px #00000045;
      padding: 30px 50px;
      border-radius: 58px;
    }
  }

  .service-card__image-container {
    grid-column: 1;
    grid-row: 1;
    height: 550px;
    width: 400px;
    margin: auto;
    border-radius: 58px;
    padding: 50px;
    background: #fff;
    box-shadow: inset 3px 3px 2px #00000045;

    img {
      border-radius: 40px;
      box-shadow: 3px 3px 2px #00000045;
    }
  }
}
</style>
