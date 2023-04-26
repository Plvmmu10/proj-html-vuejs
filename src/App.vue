<template>
  <!-- Header with top-header and navbar -->
  <header>
    <TopHeader />
    <hr class="text-white p-0 m-0">
    <NavbarComponent />
  </header>

  <!-- Main with jumbo and all the sections -->
  <main>
    <MainComponent />
  </main>
</template>

<script>
import TopHeader from './components/TopHeader.vue';
import NavbarComponent from './components/NavbarComponent.vue';
import MainComponent from './components/MainComponent.vue';
export default {
  components: {
    TopHeader,
    NavbarComponent,
    MainComponent
  }
}
</script>

<style lang="scss" scoped></style>