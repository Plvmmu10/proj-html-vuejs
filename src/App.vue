<template>
  <!-- Header with top-header and navbar -->
  <header>
    <HeaderComponent />
  </header>

  <!-- Main with jumbo and all the sections -->
  <main>
    <MainComponent />
  </main>

  <footer>
    <FooterComponent />
  </footer>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import MainComponent from './components/MainComponent.vue';
import FooterComponent from './components/FooterComponent.vue';
export default {
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent
  }
}
</script>

<style lang="scss" scoped>
footer {
  background-image: url('/img/footer-bg.png');
}
</style>