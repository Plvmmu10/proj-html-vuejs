<template>
    <div class="myContainer">
        <div class="d-flex flex-column align-items-center">
            <h1 class="text-white">{{ title }}</h1>
            <div class="horizontal"></div>

            <TopSlider :listItem="topListItem" :listArray="topListArray" />
        </div>

        <div class="position-relative">
            <div class="d-flex flex-nowrap row" ref="sliderContainer">
                <SliderCard v-for="(slide, index) in sliderArray" :key="index" :item="slide" />
            </div>
            <!-- Change slide buttons -->
            <button class="prevBtn myBtn" @click="prevCard">
                <i class="fa-solid fa-chevron-left"></i>
            </button>

            <button class="nextBtn myBtn" @click="nextCard">
                <i class="fa-solid fa-chevron-right"></i>
            </button>
        </div>
    </div>
</template>

<script>
import TopSlider from './TopSlider.vue';
import SliderCard from './SliderCard.vue';
export default {
    name: 'SliderComponent',
    components: {
        TopSlider,
        SliderCard
    },
    props: [
        'slide',
        'sliderArray',
        'title',
        'topListItem',
        'topListArray',
        'index'
    ],
    data() {
        return {
            sliderContainer: null,
            sliderWidth: null
        }
    },
    methods: {
        nextCard() {
            this.sliderContainer.scrollBy(this.sliderWidth / 4, 0);

            if ((this.sliderContainer.scrollLeft + this.sliderWidth + 6) >= this.sliderContainer.scrollWidth) {
                this.sliderContainer.scrollLeft = 0
            }
        },
        prevCard() {
            this.sliderContainer.scrollBy(- this.sliderWidth / 4, 0);

            if (this.sliderContainer.scrollLeft === 0) {
                this.sliderContainer.scrollLeft = this.sliderContainer.scrollWidth
            }
        }
    },
    mounted() {
        this.sliderContainer = this.$refs.sliderContainer;
        this.sliderWidth = this.sliderContainer.offsetWidth;
    }

}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

hr {
    width: 50px;
    color: $secondary-color;
}

.myBtn {
    width: 35px;
    height: 35px;
    border-radius: 50%;
    background-color: transparent;
    border: 1px solid rgb(211, 211, 211, 1);
    color: rgb(211, 211, 211, 1);
    display: flex;
    align-items: center;
    justify-content: center;
    transition: .3s;

    i {
        font-size: 15px;
    }

    &:hover {
        color: $secondary-color;
        background-color: $light-color;
    }
}

.prevBtn {
    position: absolute;
    left: -2%;
    bottom: 50%;
    z-index: 1000;
    translate: 0% -80%;
}

.nextBtn {
    position: absolute;
    right: -2%;
    bottom: 50%;
    translate: 0% -80%;
}

.row {
    overflow-x: auto;
    overflow-y: hidden;

    // Scrollbar config
    &::-webkit-scrollbar {
        display: none;
    }

    -ms-overflow-style:none;

    scrollbar-width:none;

    scroll-behavior: smooth;

}

.active {
    opacity: 1;
}

.deactive {
    opacity: 0;
}
</style>