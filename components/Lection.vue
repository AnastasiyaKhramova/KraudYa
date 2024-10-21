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
      <div class="lection">
        <img class="lection__img" src="../assets/img/picture_2.png" alt="" />
        <div class="lection_block">
          <div class="lection__desc">
            <h2 class="lection__desc_title" style="width: 698px">
              и Сеанс
              <span>одновременной игры в шахматы на 160 досках</span> гроссмейстера О. Бендера
            </h2>
            <table>
              <tbody>
                <tr>
                  <td>
                    <p>Место проведения:</p>
                  </td>
                  <td>
                    <p>Клуб «Картонажник»</p>
                  </td>
                </tr>
                <tr>
                  <td>
                    <p>Дата и время мероприятия:</p>
                  </td>
                  <td>
                    <p>22 июня 1927 г. в 18:00</p>
                  </td>
                </tr>
                <tr>
                  <td>
                    <p>Стоимость входных билетов:</p>
                  </td>
                  <td>
                    <p>20 коп.</p>
                  </td>
                </tr>
                <tr>
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
                    <p style="display: flex; gap: 12px;"><span style="color: #313131; text-decoration: line-through #F54932">100 руб.</span> 21 руб. 16 коп.</p>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
          <p class="lection-question">По всем вопросам обращаться в администрацию к К. Михельсону</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.lections {
  margin-top: 80px;
  margin-bottom: 200px;
  display: flex;
  flex-direction: column;
  gap: 64px;
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
    width: 474px;
    height: 527px;

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
    }
  }

  &__desc {
    display: flex;
    flex-direction: column;
    gap: 60px;

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

table {
  border-collapse: collapse;
}

td {
  font-family: $title-font;
  font-size: 1.25rem;
  color: $textcolor-dark;
  opacity: 70%;
  border-right: 2px #D0D0D0 solid;
  border-bottom: 2px #D0D0D0 solid;
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
  vertical-align: middle;
}

.sale span {
  color: $textcolor-dark;

}

.lection-question {
  font-family: $title-font;
  font-size: 1.25rem;
  color: #3057A2;
  line-height: 120%;
  margin-top: 3rem;
}
</style>
