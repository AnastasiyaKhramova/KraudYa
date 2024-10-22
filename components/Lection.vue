<template>
  <section class="container">
    <div class="second-container lections">
      <div class="lection">
        <h2 class="lection__desc_title">
          Чтобы поддержать Международный васюкинский турнир посетите лекцию на
          тему:
          <span>«Плодотворная дебютная идея»</span>
        </h2>
        <img src="../assets/img/picture_1.png" alt="" />
      </div>
      <div class="play-container">
        <img class="lection__img" src="../assets/img/picture_2.png" alt="" />
        <div class="play">
          <div class="lection__desc">
            <h2 class="lection__desc_title" style="width: 658px">
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
        {
          id: uuidv4(),
          activity: "Плата за игру:",
          desc: "50 коп.",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.lections {
  margin-top: 80px;
  display: flex;
  flex-direction: column;
  gap: 66px;
}

.lection {
  min-height: 250px;
  display: flex;
  align-items: center;
  justify-content: space-between;

  &_block {
    display: flex;
    flex-direction: column;
  }

  & span {
    color: $spancolor;
    font-weight: bold;
  }

  &__img {
    width: 535px;
    height: 564px;
    display: block;
    position: relative;
    bottom: 26px;
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
</style>
