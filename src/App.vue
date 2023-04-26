<template>
  <!-- Header with top-header and navbar -->
  <header>
    <HeaderComponent />
  </header>

  <!-- Main with jumbo and all the sections -->
  <main>
    <MainComponent />
  </main>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
export default {
  components: {
    HeaderComponent,
    MainComponent
  }
}
</script>

<style lang="scss" scoped></style>