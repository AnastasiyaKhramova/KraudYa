<template>
  <section class="container">
    <div class="second-container transform">
      <h1 class="transform_title">
        Этапы преображения Васюков
        <span> Будущие источники обогащения васюкинцев </span>
      </h1>
      <div class="transform__cards">
        <div v-for="(transform, index) in transforms" :key="transform.id"
          :class="'transform__cards_block block' + (index + 1)">
          <p class="transform__cards_number">{{ transform.number }}</p>
          <p class="transform__cards_text">{{ transform.desc }}</p>
        </div>
      </div>
      <img class="decor" src="../assets/img/airplane.png" alt="airplane" />
      <Slider class="slider">
        <div class="transform__slide">
          <div class="transform__slide_container">
            <p class="transform__cards_number">1</p>
            <p class="transform__cards_text">
              Строительство железнодорожной магистрали Москва-Васюки
            </p>
          </div>
          <div class="transform__slide_container">
            <p class="transform__cards_number">2</p>
            <p class="transform__cards_text">
              Открытие фешенебельной гостиницы «Проходная пешка» и других небоскрёбов
            </p>
          </div>
        </div>
        <div class="transform__slide">
          <div class="transform__slide_container">
            <p class="transform__cards_number">3</p>
            <p class="transform__cards_text">
              Поднятие сельского хозяйства в радиусе на тысячу километров:
              производство овощей, фруктов, икры, шоколадных конфет
            </p>
          </div>
        </div>
        <div class="transform__slide">
          <div class="transform__slide_container">
            <p class="transform__cards_number">4</p>
            <p class="transform__cards_text">Строительство дворца для турнира</p>
          </div>
          <div class="transform__slide_container">
            <p class="transform__cards_number">5</p>
            <p class="transform__cards_text">
              Размещение гаражей для гостевого автотранспорта
            </p>
          </div>
        </div>
        <div class="transform__slide">
          <div class="transform__slide_container">
            <p class="transform__cards_number">6</p>
            <p class="transform__cards_text">
              Постройка сверхмощной радиостанции для передачи всему миру сенсационных результатов
            </p>
          </div>
        </div>
        <div class="transform__slide">
          <div class="transform__slide_container">
            <p class="transform__cards_number">7</p>
            <p class="transform__cards_text">
              Создание аэропорта «Большие Васюки» с регулярным отправлением почтовых самолётов и дирижаблей во все концы
              света, включая
              Лос-Анжелос и Мельбурн
            </p>
          </div>
        </div>
      </Slider>
    </div>
  </section>
</template>

<script>
import { v4 as uuidv4 } from "uuid";
import Slider from "./Slider.vue";

export default {
  data() {
    return {
      transforms: [
        {
          id: uuidv4(),
          number: "1",
          desc: "Строительство железнодорожной магистрали Москва-Васюки",
        },
        {
          id: uuidv4(),
          number: "2",
          desc: "Открытие фешенебельной гостиницы «Проходная пешка» и других небоскрёбов",
        },
        {
          id: uuidv4(),
          number: "3",
          desc: "Поднятие сельского хозяйства в радиусе на тысячу километров: производство овощей, фруктов, икры, шоколадных конфет",
        },
        { id: uuidv4(), number: "4", desc: "Строительство дворца для турнира" },
        {
          id: uuidv4(),
          number: "5",
          desc: "Размещение гаражей для гостевого автотранспорта",
        },
        {
          id: uuidv4(),
          number: "6",
          desc: "Постройка сверхмощной радиостанции для передачи всему миру сенсационных результатов",
        },
        {
          id: uuidv4(),
          number: "7",
          desc: "Создание аэропорта «Большие Васюки» с регулярным отправлением почтовых самолётов и дирижаблей во все концы света, включая Лос-Анжелос и Мельбурн",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.transform {
  position: relative;
  margin-top: 113px;
  margin-bottom: 200px;

  &_title {
    width: 806px;
    font-family: $text-font;
    font-size: 3.375rem;
    font-weight: normal;
    color: $textcolor-dark;
    text-transform: uppercase;

    & span {
      display: inline-block;
      width: 280px;
      font-family: $title-font;
      font-weight: normal;
      font-size: 1.25rem;
      color: $textcomment;
      text-transform: none;
      padding-left: 7px;
      line-height: 141%;
      margin-bottom: 58px;
    }
  }

  &__cards {
    display: grid;
    gap: 20px;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 112px 112px 136px;

    &::before {
      content: "";
      position: absolute;
      top: 183px;
      width: 100%;
      height: 400px;
      background: url(../assets/img/background.png) no-repeat center center;
      background-size: cover;
      opacity: 0.1;
      z-index: 1;
    }

    &_block {
      padding: 20px;
      display: flex;
      gap: 16px;
      background: url(../assets/img/background-block.png);
      z-index: 2;
    }

    .block3 {
      grid-column: 3 / span 1;
      grid-row: 1 / span 2;
    }

    .block4 {
      grid-column: 1;
      grid-row: 2;
    }

    .block5 {
      grid-column: 2;
      grid-row: 2;
    }

    .block6 {
      grid-column: 1;
      grid-row: 3;
    }

    .block7 {
      grid-column: 2 / span 2;
      grid-row: 3;
    }

    &_number {
      min-width: 36px;
      height: 36px;
      background: $textcolor-light;
      border-radius: 18px;
      font-family: $title-font;
      font-weight: 600;
      font-size: 1.25rem;
      color: $textcolor-dark;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    &_text {
      font-family: $title-font;
      font-weight: 500;
      font-size: 1.25rem;
      color: $textcolor-dark;
      max-width: 446px;
    }
  }
}

.decor {
  position: absolute;
  bottom: -2px;
  right: -63px;
  z-index: 3;
}

@media screen and (max-width: 375px) {
  .transform {
    margin-top: 120px;

    &_title {
      width: 335px;
      font-size: 2.25rem;
      line-height: 110%;

      & span {
        width: 322px;
        font-size: 1.125rem;
        padding-left: 0;
        margin-top: 14px;
        line-height: 110%;
      }
    }

    &__slide {
      width: 335px;
      max-height: 176px;
      background: url(/_nuxt/assets/img/background-block.png);
      display: flex;
      flex-direction: column;
      align-items: center;
      padding: 62px 20px;
      gap: 28px;

      &::before {
        top: 231px;
        width: 100%;
        height: 300px;
        z-index: 0;
      }

      &_container {
        width: 295px;
        display: flex;
        gap: 0.5rem;
      }
    }

    &__cards {
      display: none;

      &_text {
        font-size: 1.125rem;
        max-width: 250px;
        padding-left: 9px;
      }
    }
  }

  .decor {
    width: 350px;
    top: 191px;
    right: -24px;
  }
}
</style>
