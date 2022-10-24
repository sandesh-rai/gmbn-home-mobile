<template>
  <div>
    <TheHeader/>
    <HomePage/>
    <TheFooter/>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';
import HomePage from './components/pages/HomePage.vue';

export default {
  name: 'App',
  components: {
    TheHeader,
    TheFooter,
    HomePage
}
}
</script>

<style>
body {
  margin: 0;
}
</style>
