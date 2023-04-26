<template>
    <div>
        <JumbotronComponent />

        <MainNav />

        <!-- First section with 'jumboCards' -->
        <section>
            <div class="row myContainer">
                <JumboCard v-for="item in jContentFirst" :item="item" />
            </div>
        </section>

        <!-- Special Category Section -->
        <section class="row myContainer py-5">
            <SpecialComponent />
        </section>

        <!-- First Slider with Our Products -->
        <section>
            <SliderComponent :sliderArray="productsList" :slide="productsList.object" :title="titlePro"
                :topListItem="navItemFirst.object" :topListArray="navItemFirst" />
        </section>
    </div>
</template>

<script>
import JumbotronComponent from './JumbotronComponent.vue';
import MainNav from './MainNav.vue';
import JumboCard from './JumboCard.vue';
import SpecialComponent from './SpecialComponent.vue';
import SliderComponent from './SliderComponent.vue';
export default {
    name: 'MainComponent',
    components: {
        JumbotronComponent,
        MainNav,
        JumboCard,
        SpecialComponent,
        SliderComponent
    },
    data() {
        return {
            jContentFirst: [
                {
                    genre: 'Most Popular',
                    text: 'The Battlefield 4 Naval Strike',
                    img: 'img/cms-banner-01.jpg'
                },
                {
                    genre: 'Latest Game',
                    text: "Assassin's Creed Unity Game",
                    img: 'img/cms-banner-02.jpg'
                }
            ],
            jContentSecond: [
                {
                    genre: '20% Discount',
                    text: "Dragon's Dogma Video Game",
                    img: 'img/cms-banner-03.jpg'
                },
                {
                    genre: '30% Discount',
                    text: 'World Of Tanks New Game',
                    img: 'img/cms-banner-04.jpg'
                }
            ],
            productsList: [
                {
                    img: 'img/01.jpg',
                    rating: 4,
                    name: 'Shopping Mahjang connect',
                    firstPrice: `&pound;180.00`,
                    secondPrice: `&pound;100.00`
                }
            ],
            dealList: [

            ],
            navItemFirst: [
                'Featured',
                'New Arrival',
                'Best Sellers'
            ],
            navItemSecond: [
                '1026 days',
                '13 hours',
                '24 mins',
                '17 secs'
            ],
            titlePro: 'Our Products',
            titleDeal: 'Deal Of The Day'

        }
    }
}
</script>

<style lang="scss" scoped></style>