<template>
  <base-layout>
    <home-page />
  </base-layout>
</template>

<script>
import BaseLayout from './components/BaseLayout.vue'; // Import the BaseLayout component
import HomePage from './components/HomePage.vue'; // Import the HomePage component

export default {
  components: {
    'base-layout': BaseLayout,
    'home-page': HomePage,
  },
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
