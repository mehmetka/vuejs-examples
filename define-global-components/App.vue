<template>
  <main>
    <HomePage />
  </main>
</template>

<script>
import HomePage from './components/HomePage.vue';

export default {
  name: 'App',
  // No longer have to register it here.
  // components: {
  //   HomePage,
  // },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
