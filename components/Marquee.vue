<template>
  <div class="container">
    <div class="marquee">
      <p>
        Дело помощи утопающим — дело рук самих утопающих! Шахматы двигают вперёд
        не только культуру, но и экономику! Лёд тронулся, господа присяжные
        заседатели!
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.marquee {
  width: 100%;
  height: 3.75rem;
  background-color: $spancolor;
  overflow: hidden;
  white-space: nowrap;
  display: flex;
  align-items: center;
  box-sizing: border-box;
}

.marquee p {
  font-family: $text-font;
  font-weight: normal;
  font-size: 1.375rem;
  display: inline-block;
  color: $textcolor-light;
  padding-left: 50%;
  text-align: center;
  text-transform: uppercase;
  animation: marquee 50s linear infinite;
}

@keyframes marquee {
  0% {
    transform: translateX(100%);
  }

  100% {
    transform: translateX(-100%);
  }
}

@media screen and (max-width: 375px) {
  .marquee {
    height: 2.375rem;
    position: relative;
    bottom: 27px;
  }

  .marquee p {
  font-size: 1rem;
  }
}
</style>
