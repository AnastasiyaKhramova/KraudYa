<template>
  <button class="button" :style="combinedStyles" @mouseover="hover = true" @mouseleave="hover = false">
    {{ btnName }}
  </button>
</template>

<script>
export default {
  props: {
    buttonColor: {
      type: String,
      default: "var(--color-dark)",
    },
    textColor: {
      type: String,
      default: "var(--textcolor-light)",
    },
    btnBorder: {
      type: String,
      default: "2px solid var(--color-dark)",
    },
    btnName: {
      type: String,
      default: "Поддержать шахматную мысль",
    },
    hoverButtonColor: {
      type: String,
      default: "var(--hover-color)",
    },
    hoverTextColor: {
      type: String,
      default: "var(--textcolor-dark)",
    },
    hoverBorderColor: {
      type: String,
      default: "none"
    }
  },
  data() {
    return {
      hover: false,
    };
  },
  computed: {
    combinedStyles() {
      return this.hover
        ? {
          backgroundColor: this.hoverButtonColor,
          color: this.hoverTextColor,
          border: this.hoverBorderColor,
        }
        : {
          backgroundColor: this.buttonColor,
          color: this.textColor,
          border: this.btnBorder,
        };
    },
  },
};
</script>

<style scoped>
.button {
  font-family: var(--titlefont);
  font-weight: 500;
  font-size: 1rem;
  width: 263px;
  height: 72px;
  border-radius: 66px;
  padding: 20px 49px;
  display: flex;
  align-items: center;
  transition: background-color 0.3s ease, color 0.3s ease, border-color 0.3s ease;
  z-index: 1;
}

@media screen and (max-width: 375px) {
  .button {
  width: 335px;
  height: 47px;
  padding: 1px 41px;
}
}
</style>
