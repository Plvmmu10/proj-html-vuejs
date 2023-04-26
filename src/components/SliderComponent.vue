<template>
    <div class="myContainer">
        <div class="d-flex flex-column align-items-center">
            <h1 class="text-white">{{ title }}</h1>
            <div class="horizontal"></div>

            <TopSlider :listItem="topListItem" :listArray="topListArray" />
        </div>

        <div class="row">
            <SliderCard v-for="slide in sliderArray" :item="slide" />
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
        'topListArray'
    ],
    data() {
        return {
        }
    }

}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;

hr {
    width: 50px;
    color: $secondary-color;
}
</style>