<template>
  <main>
    <section class="latest-videos">
      <h3>
        Latest Videos
      </h3>
      <article class="video-row" v-for="video in videos" :key="video._id">
        <a :href="`https://www.globalcyclingnetwork.com/video/${video.urlTitle}`">
          <img :src="`https://img.youtube.com/vi/${video._id}/mqdefault.jpg`" alt="video.title"/>
          <h6>{{formatDate(video.publishDate)}}</h6>
          <h4>{{video.title}}</h4>
        </a>
      </article>
    </section>
  </main>
</template>

<script>
import axios from 'axios'
import moment from 'moment'
export default {
  name: 'HomePage',
  data () {
    return {
      videos: [],
      scrollPage: 1,
      scrollLoading: false,
    }
  },
  methods: {
    formatDate(date) {
      return moment(date).format("Do MMMM YYYY")
    },
    getInitialVideos() {
      axios
      .get('http://localhost:8080/api/videos')
      .then(response => (this.videos = response.data.videos))
    },
    getNextVideos(){
      axios.get(`http://localhost:8080/api/videos?limit=12&offset=${12*this.scrollPage}`)
      .then(response => {
            this.videos = [...this.videos, ...response.data.videos];
            this.scrollPage += 1;
            this.scrollLoading = false;
          });
    },
    handleScroll() {
			if (
				(window.scrollY + window.innerHeight >= document.body.scrollHeight - 50) && !this.scrollLoading
			) {
        this.scrollLoading = true;
        this.getNextVideos();
			}
		},
  },
  beforeMount() {
    this.getInitialVideos();
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll);
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
section.latest-videos h3 {
  font-size: 1.5em;
  margin: 0.5em 0.5em 0em;
}

article.video-row {
  padding: 1em;
}

article.video-row:hover, article.video-row:focus {
  background-color: rgba(240, 240, 240, 0.64);
}

article.video-row a{
  text-decoration: none;
  color: black;
}

article.video-row img {
  width: 100%;
}

article.video-row h6 {
  margin: 0.3rem 0;
  font-size: 0.88rem;
  font-weight: 700;
  letter-spacing: -0.01rem;
}

article.video-row h4 {
  margin: 0px;
  font-size: 1rem;
  line-height: 1.25;
  font-weight: 500;
  letter-spacing: -0.01rem;
}
</style>
