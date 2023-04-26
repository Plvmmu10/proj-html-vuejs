<template>
  <!-- Header with top-header and navbar -->
  <header>
    <TopHeader />
    <hr class="text-white p-0 m-0">
    <NavbarComponent />
  </header>
</template>

<script>
import TopHeader from './components/TopHeader.vue';
import NavbarComponent from './components/NavbarComponent.vue';
export default {
  components: {
    TopHeader,
    NavbarComponent
  }
}
</script>

<style lang="scss" scoped></style>