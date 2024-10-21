<template>
  <section class="container">
    <div class="second-container lections">
      <div class="lection">
        <h2 class="lection__title">
          Чтобы поддержать Международный васюкинский турнир посетите лекцию на
          тему:
          <span>«Плодотворная дебютная идея»</span>
        </h2>
        <img src="../assets/img/picture_1.png" alt="" />
      </div>
      <div>
        <img class="lection__img" src="../assets/img/picture_2.png" alt="" />
        <h2 class="lection__title" style="width: 704px">
          и Сеанс
          <span>одновременной игры в шахматы на 160 досках</span> гроссмейстера
          О. Бендера
        </h2>
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

  &__title {
    width: 764px;
    height: 195.43px;
    font-family: $text-font;
    font-weight: normal;
    font-size: 2.25rem;
    line-height: 135%;
    text-transform: uppercase;
  }

  & span {
    color: $spancolor;
    font-weight: bold;
  }

  &__img {
    width: 474px;
    height: 527px;
  }
}
</style>
