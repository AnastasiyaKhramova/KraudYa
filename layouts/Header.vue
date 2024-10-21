<template>
  <header class="container header">
    <div class="second-container">
      <div class="logo">
        <div>
          <img class="logo_img" v-for="(n, index) in 4" :key="index" src="../assets/img/logo.png" alt="logo" />
        </div>
        <div class="logo_text">
          <p>клуб</p>
          <p>четырех коней</p>
        </div>
      </div>
      <div class="headding">
        <div class="title">
          <h1>
            Превратите уездный город
            <span>в столицу земного шара</span>
          </h1>
        </div>
        <p class="title_desc">
          Оплатите взнос на телеграммы для организации Международного
          васюкинского турнира по шахматам
        </p>
        <div class="btn-position">
          <Button />
          <Button :buttonColor="buttonColor" :textColor="textColor" :btnName="btnName" />
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import Button from "~/components/Button.vue";
export default {
  data() {
    return {
      btnName: "Подробнее о турнире",
      buttonColor: "$textcolor-light",
      textColor: "$color-dark"
    };
  },
};
</script>

<style lang="scss" scoped>
.header {
  height: 700px;
  background: url(../assets/img/main_desktop.png) no-repeat center center;
  background-size: cover;

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 700px;
    background: url(../assets/img/background.png) no-repeat center center;
    background-size: cover;
    opacity: 0.1;
    z-index: 1;
  }
}

.logo {
  padding-top: 26px;
  display: flex;
  gap: 6px;
  color: #595653;
  height: 36px;
  font-family: $title-font;
  font-weight: bold;
  font-size: 16.65px;
  line-height: 108%;
  text-transform: uppercase;

  &_img {
    width: 21.65px;
    height: 32.18px;
    margin-right: 1.73px;
  }

  &_text {
    width: 147px;
    display: flex;
    flex-direction: column;
  }
}

.btn-position {
  display: flex;
  gap: 1rem;
}

.headding {
  width: 542px;
}

.title {
  margin-top: 62px;
  margin-bottom: 24px;

  & h1 {
    font-family: $text-font;
    font-weight: normal;
    font-size: 3.75rem;
    color: $textcolor-dark;
    text-transform: uppercase;
    line-height: 110%;
  }

  & span {
    display: flex;
    text-align: center;
  }

  &_desc {
    font-family: $title-font;
    font-weight: normal;
    font-size: 1.125rem;
    color: $textcolor-dark;
    line-height: 130%;
    margin-bottom: 40px;
    text-align: center;
  }
}
</style>
