<template>
    <section class="container">
        <div class="second-container transform">
            <h1 class="transform_title">Этапы преображения Васюков
                <span>
                    Будущие источники обогащения васюкинцев
                </span>
            </h1>
            <div class="transform__cards">
                <div class="transform__cards_block" v-for="transform in transforms" :key="transform.id">
                    <p class="transform__cards_number">{{ transform.number }}</p>
                    <p class="transform__cards_text">{{ transform.desc }}</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
export default {
    data() {
        return {
            transforms: [
                {
                    id: uuidv4(),
                    number: '1',
                    desc: 'Строительство железнодорожной магистрали Москва-Васюки'
                },
                {
                    id: uuidv4(),
                    number: '2',
                    desc: 'Открытие фешенебельной гостиницы «Проходная пешка» и других небоскрёбов'
                },
                {
                    id: uuidv4(),
                    number: '3',
                    desc: 'Поднятие сельского хозяйства в радиусе на тысячу километров: производство овощей, фруктов, икры, шоколадных конфет'
                },
                {
                    id: uuidv4(),
                    number: '4',
                    desc: 'Строительство дворца для турнира'
                },
                {
                    id: uuidv4(),
                    number: '5',
                    desc: 'Размещение гаражей для гостевого автотранспорта'
                },
                {
                    id: uuidv4(),
                    number: '6',
                    desc: 'Постройка сверхмощной радиостанции для передачи всему миру сенсационных результатов'
                },
                {
                    id: uuidv4(),
                    number: '7',
                    desc: 'Создание аэропорта «Большие Васюки» с регулярным отправлением почтовых самолётов и дирижаблей во все концы света, включая Лос-Анжелос и Мельбурн'
                }
            ]
        }
    },
}
</script>
<style lang="scss" scoped>
.transform {

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
            color: #3057A2;
            text-transform: none;
        }
    }

    &__cards {
        display: grid;
        gap: 20px;
        grid-template-columns: repeat(3, 1fr);

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

        &_block {
            padding: 20px;
            display: flex;
            gap: 1rem;
            background: url(../assets/img/background-block.png);
            // min-width: 394px;
            // min-height: 112px;
        }
    }
}
</style>