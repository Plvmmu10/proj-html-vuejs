<template>
    <div class="myContainer py-4 d-flex justify-content-between">
        <!-- Site logo -->
        <div class="logo-container align-items-center">
            <img src="img/logo.png" alt="logo" class="w-100 h-100">
        </div>

        <!-- Navbar items -->
        <div>
            <ul class="d-flex h-100 align-items-center">
                <li v-for="(item, index) in navArray" :key="index" class="px-4">
                    <a href="#" @mouseover="getActive(index)" :class="index === currentIndex ? 'active' : ''">{{ item }}</a>
                </li>
            </ul>
        </div>

        <!-- User utilities -->
        <div class="text-white d-flex align-items-center">

            <i class="fa-solid fa-magnifying-glass"></i>
            <i class="fa-regular fa-user px-4"></i>

            <div class="d-flex align-items-center">
                <i class="fa-solid fa-bag-shopping px-2"></i>
                <p class="bag-price m-0">(0) &pound;0.00</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NavbarComponent',
    props: ['navArray'],
    data() {
        return {
            currentIndex: true
        }
    },
    methods: {
        getActive(index) {
            this.currentIndex = index
        }
    }
}
</script>

<style lang="scss" scoped>
@use '../assets/style/partials/variables' as *;


a {
    text-decoration: none;
    color: white;
}


.active {
    color: $secondary-color;
}

.bag-price {
    color: $secondary-color;
}
</style>