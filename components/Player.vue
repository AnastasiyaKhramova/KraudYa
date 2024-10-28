<template>
    <section class="container">
        <div class="second-container player">
            <div class="player__headding">
                <h1 class="player__headding_title">Участники турнира</h1>
                <div class="player__headding_choice">
                    <button class="controls" @click="prevSlide" :disabled="currentPage === 0">
                        <svg width="12" height="20" viewBox="0 0 12 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M10.5382 18.4615L2.07666 9.99995L10.5382 1.53841" stroke="white" stroke-width="2"
                                stroke-linecap="square" />
                        </svg>
                    </button>
                    <p class="player_page">{{ displayedItems }}/{{ slides.length }}</p>
                    <button class="controls" @click="nextSlide" :disabled="currentPage === maxPage">
                        <svg width="12" height="20" viewBox="0 0 12 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M1.4618 1.5384L9.92334 9.99994L1.4618 18.4615" stroke="white" stroke-width="2"
                                stroke-linecap="square" />
                        </svg>

                    </button>
                </div>
            </div>
            <div class="slider">
                <div class="slide" v-for="slide in visibleSections" :key="slide.id">
                    <img class="slide__img" :src="slide.photo" alt="Photo" />
                    <h3 class="slide__title">{{ slide.name }}</h3>
                    <h4 class="slide__subtitle">{{ slide.class }}</h4>
                    <button class="slide__btn">Подробнее</button>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import { v4 as uuidv4 } from "uuid";
import photo from "../assets/img/photo.png";

export default {
    data() {
        return {
            slides: [
                { id: uuidv4(), photo: photo, name: "Хозе-Рауль Капабланка", class: "Чемпион мира по шахматам" },
                { id: uuidv4(), photo: photo, name: "Эммануил Ласкер", class: "Чемпион мира по шахматам" },
                { id: uuidv4(), photo: photo, name: "Александр Алехин", class: "Чемпион мира по шахматам" },
                { id: uuidv4(), photo: photo, name: "Арон Нимцович", class: "Чемпион мира по шахматам" },
                { id: uuidv4(), photo: photo, name: "Рихард Рети", class: "Чемпион мира по шахматам" },
                { id: uuidv4(), photo: photo, name: "Остап Бендер", class: "Гроссмейстер" },
            ],
            currentPage: 0,
            itemsPerPage: 3,
        };
    },
    computed: {
        pageCount() {
            return Math.ceil(this.slides.length / this.itemsPerPage);
        },
        visibleSections() {
            const start = this.currentPage * this.itemsPerPage;
            return this.slides.slice(start, start + this.itemsPerPage);
        },
        maxPage() {
            return this.pageCount - 1;
        },
        displayedItems() {
            const count = (this.currentPage + 1) * this.itemsPerPage;
            return count > this.slides.length ? this.slides.length : count;
        },
    },
    methods: {
        calculateItemsPerPage() {
            if (window.innerWidth <= 480) {
                return 1;
            } else if (window.innerWidth <= 768) {
                return 2;
            } else {
                return 3;
            }
        },
        prevSlide() {
            if (this.currentPage > 0) {
                this.currentPage--;
            }
        },
        nextSlide() {
            if (this.currentPage < this.maxPage) {
                this.currentPage++;
            }
        },
        handleResize() {
            const newItemsPerPage = this.calculateItemsPerPage();
            if (newItemsPerPage !== this.itemsPerPage) {
                this.itemsPerPage = newItemsPerPage;
                this.currentPage = 0;
            }
        },
    },
    mounted() {
        this.itemsPerPage = this.calculateItemsPerPage();
        window.addEventListener("resize", this.handleResize);
    },
    beforeUnmount() {
        window.removeEventListener("resize", this.handleResize);
    },
};
</script>

<style scoped>
/* Styles here */
</style>


<style lang="scss" scoped>
.player {
    display: flex;
    flex-direction: column;
    margin-bottom: 138px;

    &__headding {
        display: flex;
        justify-content: space-between;
        margin-bottom: 60px;

        &_title {
            font-family: $text-font;
            font-weight: normal;
            font-size: 3.375rem;
            color: $textcolor-dark;
            text-transform: uppercase;
        }

        &_choice {
            display: flex;
            gap: 19px;
            align-items: center;
            font-family: $title-font;
            font-weight: normal;
            font-size: 1rem;
            color: $textcolor-dark;
        }
    }
}

.controls {
    width: 44px;
    height: 44px;
    background-color: $textcolor-dark;
    border: 1px solid $textcolor-dark;
    border-radius: 50px;
    cursor: pointer;
}

.slider {
    display: flex;
    gap: 20px;
}

.slide {
    width: 394px;
    height: 462px;
    display: flex;
    flex-direction: column;
    align-items: center;

    &__img {
        width: 320px;
        height: 320px;
    }

    &__title {
        font-family: $title-font;
        font-size: 1.5rem;
        font-weight: 600;
        color: $textcolor-dark;
        margin-top: 26px;
        margin-bottom: 7px;
    }

    &__subtitle {
        font-family: $title-font;
        font-size: 1.25rem;
        font-weight: normal;
        color: $textcolor-dark;
        opacity: 60%;
        margin-bottom: 18px;
    }

    &__btn {
        width: 113px;
        height: 35px;
        border: 1px solid $textcomment;
        background: $backgroundcolor;
        border-radius: 62px;
        color: $textcomment;
        font-family: $title-font;
        font-size: 1rem;
        font-weight: 500;
        text-align: center;

        &:hover {
          background-color: $textcomment;
          color: $textcolor-light;
        }
    }
}

@media screen and (max-width: 375px) {
    .player {
        margin-bottom: 177px;

        &__headding {
            margin-bottom: 60px;
            flex-direction: column;

            &_title {
                order: 1;
                font-size: 2.25rem;
                line-height: 110%;
            }

            &_choice {
                order: 3;
                display: flex;
                gap: 17px;
                margin-top: 468px;
                justify-content: center;
            }
        }
    }

    .controls {
        width: 36px;
        height: 36px;
    }

    .slider {
        order: 2;
        margin-top: -525px;
        justify-content: center;
    }

    .slide {
        width: 355px;
        height: 388px;

        &__img {
            width: 244px;
            height: 244px;
        }

        &__title {
            margin-top: 28px;
            margin-bottom: 8px;
        }

        &__subtitle {
            margin-bottom: 20px;
        }
    }
}
</style>
