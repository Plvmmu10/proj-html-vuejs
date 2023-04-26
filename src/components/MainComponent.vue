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
        <section class="py-5">
            <SliderComponent :sliderArray="productsList" :slide="productsList.object" :title="titlePro"
                :topListItem="navItemFirst.object" :topListArray="navItemFirst" />
        </section>

        <!-- Second section with 'jumboCard' -->
        <section>
            <div class="row myContainer">
                <JumboCard v-for="item in jContentSecond" :item="item" />
            </div>
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
                    firstPrice: `180.00`,
                    secondPrice: `100.00`
                },
                {
                    img: 'img/02.jpg',
                    rating: 2,
                    name: 'Logitech Headphones',
                    firstPrice: ``,
                    secondPrice: `75.00`
                },
                {
                    img: 'img/03.jpg',
                    rating: 5,
                    name: 'Boolean Red Gaming Pad',
                    firstPrice: `5000.00`,
                    secondPrice: `92.00`
                },
                {
                    img: 'img/04.jpg',
                    rating: 0,
                    name: 'Juventus Joypad Zebra',
                    firstPrice: `36.00`,
                    secondPrice: `32.00`
                },
                {
                    img: 'img/05.jpg',
                    rating: 2,
                    name: 'VR Boolean Connector',
                    firstPrice: ``,
                    secondPrice: `250.00`
                },
                {
                    img: 'img/06.jpg',
                    rating: 5,
                    name: 'Sony Gaming Headset',
                    firstPrice: `50.00`,
                    secondPrice: `40.00`
                },
                {
                    img: 'img/07.jpg',
                    rating: 2,
                    name: 'Sony Inferno Joypad',
                    firstPrice: ``,
                    secondPrice: `210.00`
                },
                {
                    img: 'img/08.jpg',
                    rating: 5,
                    name: 'Purple Tiger Joypad',
                    firstPrice: `250.00`,
                    secondPrice: `200.00`
                },
                {
                    img: 'img/09.jpg',
                    rating: 4,
                    name: 'Buddy and Lucky Solitaire',
                    firstPrice: ``,
                    secondPrice: `100.00`
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