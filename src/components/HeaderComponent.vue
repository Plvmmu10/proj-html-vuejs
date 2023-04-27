<template>
    <div>
        <TopHeader />
        <hr class="text-white p-0 m-0">
        <NavbarComponent :navArray="navItems" />
    </div>
</template>

<script>
import TopHeader from './TopHeader.vue';
import NavbarComponent from './NavbarComponent.vue';
export default {
    name: 'HeaderComponent',
    components: {
        TopHeader,
        NavbarComponent
    },
    data() {
        return {
            navItems: [
                'Home',
                'Shop',
                'Blog',
                'Media',
                'ShortCode',
                'Features'
            ]
        }
    }
}
</script>

<style lang="scss" scoped></style>