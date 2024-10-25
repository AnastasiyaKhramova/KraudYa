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
            <h2>в столицу <span>земного шара</span></h2>
          </h1>
        </div>
        <p class="title_desc">
          Оплатите взнос на телеграммы для организации Международного
          васюкинского турнира по шахматам
        </p>
        <div class="btn-position">
          <Button />
          <Button :buttonColor="buttonColor" :textColor="textColor" :btnName="btnName"
            :hoverButtonColor="hoverButtonColor" :hoverTextColor="hoverTextColor" :border="border"
            :hoverBorderColor="hoverBorderColor" style="padding: 20px 79px;" />
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
      buttonColor: "var(--textcolor-light)",
      textColor: "var(--color-dark)",
      border: "var(--color-dark)",
      hoverButtonColor: "var(--color-dark)",
      hoverTextColor: "var(--textcolor-light)",
      hoverBorderColor: "2px solid var(--color-dark)"
    };
  },
};
</script>

<style lang="scss" scoped>
.header {
  min-height: 700px;
  background: url(../assets/img/main_desktop.png) no-repeat center center;
  background-size: cover;

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    min-height: 700px;
    background: url(../assets/img/background.png) no-repeat center center;
    background-size: cover;
    opacity: 0.1;
    z-index: 0;
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

  & h1,
  h2 {
    font-family: $text-font;
    font-weight: normal;
    font-size: 3.75rem;
    color: $textcolor-dark;
    text-transform: uppercase;
    line-height: 110%;
  }

  & h2 {
    text-align: center;
  }

  & span {
    position: relative;
    left: 18px;
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

@media screen and (max-width: 375px) {
  .header {
    height: 747px;
    background: url(../assets/img/main_phone.png) no-repeat center center;

    &::before {
      min-height: 812px;
    }
  }

  .logo {
    padding-top: 18px;
    height: 32px;
    font-size: 14.42px;

    &_img {
      width: 18.75px;
      height: 27px;
      margin-right: 1.5px;
    }
  }

  .btn-position {
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .headding {
    width: 335px;
  }

  .title {
    margin-top: 40px;

    & h1,
    h2 {
      font-size: 2.25rem;
    }

    h2 {
      position: relative;
      left: 4px;
    }

    & span {
      left: 11px;
    }

    &_desc {

      text-align: start;
      margin-bottom: 32px;
    }
  }

}
</style>
