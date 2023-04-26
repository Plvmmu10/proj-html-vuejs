<template>
    <div>
        <JumbotronComponent />

        <MainNav />
    </div>
</template>

<script>
import JumbotronComponent from './JumbotronComponent.vue';
import MainNav from './MainNav.vue'
export default {
    name: 'MainComponent',
    components: {
        JumbotronComponent,
        MainNav
    }
}
</script>

<style lang="scss" scoped></style>