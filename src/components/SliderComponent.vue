<template>
    <div class="myContainer">
        <div class="d-flex flex-column align-items-center">
            <h1 class="text-white">{{ title }}</h1>
            <div class="horizontal"></div>

            <TopSlider :listItem="topListItem" :listArray="topListArray" />
        </div>

        <div class="row flex-nowrap">
            <SliderCard v-for="(slide, index) in sliderArray" :key="index" :item="slide" />

            <!-- Change slide buttons -->
            <!-- <button class="prevBtn myBtn" @click="prevCard">
                <i class="fa-solid fa-chevron-left"></i>
            </button>

            <button class="nextBtn myBtn" @click="nextCard">
                <i class="fa-solid fa-chevron-right"></i>
            </button> -->
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
            // activeSlider: [],
            currentIndex: 0,
        }
    },
    methods: {
        // addActive(currentIndex) {
        //     this.activeSlider = [];

        //     let activeIndex = currentIndex;

        //     // this.activeSlider.push(this.sliderArray[activeIndex])
        //     // this.activeSlider.push(this.sliderArray[activeIndex + 1])
        //     // this.activeSlider.push(this.sliderArray[activeIndex + 2])
        //     // this.activeSlider.push(this.sliderArray[activeIndex + 3])

        //     // this.activeSlider.push(this.sliderArray[0])
        //     // this.activeSlider.push(this.sliderArray[1])
        //     // this.activeSlider.push(this.sliderArray[2])
        //     // this.activeSlider.push(this.sliderArray[3])

        //     if ((activeIndex + 3) > this.sliderArray.length - 1) {
        //         this.activeSlider.push(this.sliderArray[0])
        //         this.activeSlider.push(this.sliderArray[1])
        //         this.activeSlider.push(this.sliderArray[2])
        //         this.activeSlider.push(this.sliderArray[3])
        //     } else {
        //         this.activeSlider.push(this.sliderArray[activeIndex])
        //         this.activeSlider.push(this.sliderArray[activeIndex + 1])
        //         this.activeSlider.push(this.sliderArray[activeIndex + 2])
        //         this.activeSlider.push(this.sliderArray[activeIndex + 3])
        //     }


        // },
        // removeActive() {
        // },
        // nextCard() {

        //     if (this.currentIndex === this.sliderArray.length - 1) {
        //         this.currentIndex = 0
        //     } else {
        //         this.currentIndex++
        //     }

        //     // this.addActive(this.currentIndex)

        // },
        // prevCard() {
        //     if (this.currentIndex === 0) {
        //         this.currentIndex = this.sliderArray.length - 1
        //     } else {
        //         this.currentIndex--
        //     }

        //     this.removeActive(this.currentIndex)

        // }               
    },
    // mounted() {
    //     this.addActive(this.currentIndex);
    // }

}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

hr {
    width: 50px;
    color: $secondary-color;
}

.row {
    position: relative;
    overflow-x: auto;
    overflow-y: hidden;

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
        left: 0;
        bottom: 50%;
        z-index: 1000;
        translate: 0% -80%;
    }

    .nextBtn {
        position: absolute;
        right: 0;
        bottom: 50%;
        translate: 0% -80%;
    }
}

.active {
    opacity: 1;
}

.deactive {
    opacity: 0;
}
</style>