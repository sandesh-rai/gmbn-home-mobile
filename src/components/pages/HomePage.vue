<template>
  <main>
    <section class="latest-videos">
      <h3>
        Latest Videos
      </h3>
      <article>

      </article>
    </section>
  </main>
</template>

<script>
import axios from 'axios'
export default {
  name: 'HomePage',
  data () {
    return {
      videoData: []
    }
  },
  mounted () {
    axios
      .get('http://localhost:8080/api/videos')
      .then(response => (this.videoData = response.data.videos))
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  font-size: 1.5em;
  margin: 0.5em;
}
</style>
