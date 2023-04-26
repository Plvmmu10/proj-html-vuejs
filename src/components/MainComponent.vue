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
        <section></section>
    </div>
</template>

<script>
import JumbotronComponent from './JumbotronComponent.vue';
import MainNav from './MainNav.vue';
import JumboCard from './JumboCard.vue';
export default {
    name: 'MainComponent',
    components: {
        JumbotronComponent,
        MainNav,
        JumboCard,
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
            ]
        }
    }
}
</script>

<style lang="scss" scoped></style>