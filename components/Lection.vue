<template>
  <section class="container">
    <div class="second-container lections">
      <div class="lection">
        <div class="lection__text">
          <h2 class="lection__desc_title">
            Чтобы поддержать Международный васюкинский турнир
            <span class="lection__desc_title-span">посетите лекцию на тему:
              <span style="color: #f54932; font-weight: bold;">«Плодотворная дебютная идея»</span></span>
          </h2>
        </div>
        <img class="lection__desc_img" src="../assets/img/picture_1.png" alt="picture" />
      </div>
      <div class="play-container">
        <img class="lection__img" src="../assets/img/picture_2.jpg" alt="picture" />
        <div class="play">
          <div class="lection__desc">
            <h2 class="lection__desc_title-play">
              и Сеанс
              <span style="color: #f54932; font-weight: bold">одновременной игры в шахматы на 160 досках</span>
              гроссмейстера О. Бендера
            </h2>
            <table>
              <tbody>
                <tr v-for="lection in lections" :key="lection.id">
                  <td>
                    <p>{{ lection.activity }}</p>
                  </td>
                  <td>
                    <p>{{ lection.desc }}</p>
                  </td>
                </tr>
                <tr class="no-break">
                  <td>
                    <p>Плата за игру:</p>
                  </td>
                  <td>
                    <p>50 коп.</p>
                  </td>
                </tr>
                <tr>
                  <td>
                    <p>Взнос на телеграммы:</p>
                  </td>
                  <td>
                    <p style="display: flex; gap: 12px">
                      <span style="
                          color: #313131;
                          text-decoration: line-through #f54932;
                        ">100 руб.</span>
                      21 руб.16 коп.
                    </p>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
          <p class="lection-question">
            По всем вопросам обращаться в администрацию к К. Михельсону
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      lections: [
        {
          id: uuidv4(),
          activity: "Место проведения:",
          desc: "Клуб «Картонажник»",
        },
        {
          id: uuidv4(),
          activity: "Дата и время мероприятия:",
          desc: "22 июня 1927 г.в 18:00",
        },
        {
          id: uuidv4(),
          activity: "Стоимость входных билетов:",
          desc: "20 коп.",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.lections {
  margin-top: 91px;
  display: flex;
  flex-direction: column;
  gap: 54px;
}

.lection {
  min-height: 250px;
  display: flex;
  align-items: center;
  justify-content: space-between;

  &__text {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
  }

  &_block {
    display: flex;
    flex-direction: column;
  }

  & span {
    text-transform: uppercase;
    font-family: $text-font;
    font-size: 2.25rem;
    font-weight: normal;
    line-height: 135%;
  }

  &__img {
    width: 535px;
    height: 610px;
    display: block;
    position: relative;
    bottom: 50px;
    left: -31px;

    &::before {
      content: "";
      position: absolute;
      top: 134px;
      width: 98%;
      height: 382px;
      background: url(../assets/img/background.png) no-repeat center center;
      background-size: cover;
      opacity: 0.1;
      z-index: 1;
    }
  }

  &__desc {
    display: flex;
    flex-direction: column;
    gap: 44px;

    &_title {
      width: 764px;
      max-height: 195.43px;
      font-family: $text-font;
      font-weight: normal;
      font-size: 2.25rem;
      line-height: 135%;
      text-transform: uppercase;
    }

    &_title-play {
      width: 658px;
      max-height: 195.43px;
      font-family: $text-font;
      font-weight: normal;
      font-size: 2.25rem;
      line-height: 135%;
      text-transform: uppercase;
    }
  }
}

.play-container {
  display: flex;
}

.play {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  position: relative;
  left: -17px;
}

table {
  border-collapse: collapse;
}

td {
  width: 150px;
  font-family: $title-font;
  font-size: 1.25rem;
  color: $textcolor-dark;
  opacity: 70%;
  border-right: 2px #d0d0d0 solid;
  border-bottom: 2px #d0d0d0 solid;
}

table tr:last-child td {
  border-bottom: 0;
}

td:last-child {
  font-weight: bold;
  opacity: 100%;
  padding-left: 1rem;
  border-right: none;
}

tr {
  height: 56px;
}

.sale span {
  color: $textcolor-dark;
}

.lection-question {
  font-family: $title-font;
  font-size: 1.25rem;
  color: $textcomment;
  line-height: 120%;
  margin-top: 2rem;
  position: relative;
  right: 7px;
}

@media screen and (max-width: 375px) {
  .lections {
    margin-top: 76px;
    gap: 24px;
    height: 1773px;
  }

  .lection {
    flex-direction: column;

    &_block {
      display: flex;
      flex-direction: column;
    }

    &__img {
      width: 374px;
      height: 433px;
      bottom: 10px;
      left: -20px;
    }

    &__desc {
      gap: 56px;
      &_title {
        order: 1;
        width: 335px;
        font-size: 1.75rem;
        margin-bottom: 264px;

        & span{
          display: block;
          font-size: 1.75rem;
        }
      }

      &_title-span {
        margin-top: 262px;
      }

      &_title-play {
        width: 335px;
        font-size: 1.75rem;
      }

      &_img {
        order: 2;
        width: 335px;
        height: 212.56px;
        position: relative;
        bottom: 304px;
      }
    }
  }

  .play-container {
    flex-direction: column;
  }

  .play {
    left: 0;
    top: -1px;
  }

  table {
    border-collapse: collapse;
    margin-top: 18px;
  }

  tr {
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-bottom: 1rem;
  }

  td {
    width: 100%;
    border-bottom: none;
    border-right: none;
  }

  td:last-child {
    padding-left: 0;
  }

  tr:nth-child(n) {
    border-bottom: 2px solid #d0d0d0;
    padding-bottom: 18px;
  }

  tr.no-break {
    height: 40px;
    flex-direction: row;
    padding-bottom: 0;
  }

  tr.no-break td {
    width: 43%;
  }

  .lection-question {
    font-size: 1.125rem;
    margin-top: 7px;
    right: 1px;
  }
}
</style>
