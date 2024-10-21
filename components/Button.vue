<template>
  <button
    class="button"
    :style="{ backgroundColor: buttonColor, color: textColor }"
  >
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
        btnName: {
            type: String,
        default: "Поддержать шахматную мысль"
    } ,
  },
};
</script>

<style lang="scss" scoped>
.button {
  font-family: $title-font;
  font-weight: 500px;
  font-size: 1rem;
  width: 263px;
  height: 72px;
  border-radius: 66px;
  border: 2px solid $color-dark;
  line-height: 130%;
  padding: 20px 49px;
  display: flex;
  align-items: center;
}
</style>
