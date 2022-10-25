<template>
  <div>
    <AppHeader @archiveSelected="(val) => selectedArchive = val"/>
    <HomePage :selectedArchive="selectedArchive"/>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import HomePage from './components/pages/HomePage.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    HomePage
  },
  data(){
    return {
      selectedArchive: null,
    }
  }
}
</script>

<style>
body {
  margin: 0;
  font-family: proxima-nova, sans-serif;
}
</style>
