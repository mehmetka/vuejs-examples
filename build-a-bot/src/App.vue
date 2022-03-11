<template>
  <!-- <header>
    Header
  </header> -->
  <main>
    <RobotBuilder />
    <!-- <SearchComponent /> -->
  </main>
</template>

<script>
// import SearchComponent from './search/SearchComponent.vue';
import RobotBuilder from './build/RobotBuilder.vue';

export default {
  name: 'app',
  components: {
    RobotBuilder,
    // SearchComponent,
  },
};
</script>

<style>
body {
  background: linear-gradient(to bottom, #555, #999);
  background-attachment: fixed;
}
</style>

<!-- We can have more than one style element. -->
<style scoped> /* Only applied to App component. */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
main {
  margin: 0 auto;
  padding: 30px;
  background-color: white;
  width: 1024px;
  min-height: 300px;
}
</style>
