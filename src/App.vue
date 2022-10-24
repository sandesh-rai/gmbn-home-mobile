<template>
  <div>
    <TheHeader/>
    <Home/>
    <TheFooter/>
  </div>
</template>

<script>
import Home from './components/Home.vue';
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';

export default {
  name: 'App',
  components: {
    Home,
    TheHeader,
    TheFooter
}
}
</script>

<style>
</style>
