<template>
  <div>
    <AppHeader/>
    <HomePage/>
    <AppFooter/>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppFooter from './components/AppFooter.vue';
import HomePage from './components/pages/HomePage.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppFooter,
    HomePage
}
}
</script>

<style>
body {
  margin: 0;
  font-family: proxima-nova, sans-serif;
}
</style>
