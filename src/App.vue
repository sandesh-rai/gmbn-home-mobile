<template>
  <div>
    <AppHeader @archiveSelected="(val) => selectedArchive = val"/>
    <p class="desktop-message">{{'Please view this page on mobile with Chrome DevTools. It has not been optimised for tablet or desktop.'}}</p>
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

<style scoped>
p.desktop-message {
  margin: 1rem;
  padding: 1rem;
  border: 4px solid red;
}

@media only screen and (max-width: 500px) {
  p.desktop-message {
    display: none;
  }
}
</style>
