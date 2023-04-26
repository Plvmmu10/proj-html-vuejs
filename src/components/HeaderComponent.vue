<template>
    <div>
        <TopHeader />
        <hr class="text-white p-0 m-0">
        <NavbarComponent />
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
    }
}
</script>

<style lang="scss" scoped></style>