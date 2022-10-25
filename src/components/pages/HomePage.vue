<template>
  <main>
    <section class="latest-videos">
      <h3>
        Latest Videos
      </h3>
      <article v-for="video in videos" :key="video._id">
        <HomePageVideoRow :video="video"/>
      </article>
    </section>
    <div v-show="scrollLoading" class="loading-spinner">
      <i class="fa-solid fa-spinner"></i>
    </div>
  </main>
</template>

<script>
import axios from 'axios'
import HomePageVideoRow from '../HomePageVideoRow.vue'
export default {
    name: "HomePage",
    data() {
        return {
            videos: [],
            scrollPage: 1,
            scrollLoading: false,
        };
    },
    methods: {
        getInitialVideos() {
            axios
                .get("http://localhost:8080/api/videos")
                .then(response => (this.videos = response.data.videos));
        },
        getNextVideos() {
            axios.get(`http://localhost:8080/api/videos?limit=12&offset=${12 * this.scrollPage}`)
                .then(response => {
                this.videos = [...this.videos, ...response.data.videos];
                this.scrollPage += 1;
                this.scrollLoading = false;
            });
        },
        handleScroll() {
            if ((window.scrollY + window.innerHeight >= document.body.scrollHeight - 50) && !this.scrollLoading) {
                this.scrollLoading = true;
                this.getNextVideos();
            }
        },
    },
    beforeMount() {
        this.getInitialVideos();
    },
    mounted() {
        window.addEventListener("scroll", this.handleScroll);
    },
    components: { HomePageVideoRow }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
section.latest-videos h3 {
  font-size: 1.5em;
  margin: 0.5em 0.5em 0em;
}

div.loading-spinner {
  display: flex;
  padding: 0.5rem 0 1rem;
}

div.loading-spinner > i {
  animation-name: spin;
  animation-duration: 1000ms;
  animation-iteration-count: infinite;
  animation-timing-function: linear; 
  font-size: 2rem;
  color: black;
  margin-left: auto;
  margin-right: auto;
}

@keyframes spin {
    from {
        transform:rotate(0deg);
    }
    to {
        transform:rotate(360deg);
    }
}
</style>
