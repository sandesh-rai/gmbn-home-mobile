<template>
    <div class="video-row">
        <a :href="`https://www.globalcyclingnetwork.com/video/${video.urlTitle}`">
          <img :src="`https://img.youtube.com/vi/${video._id}/mqdefault.jpg`" alt="video.title"/>
          <h6>{{formatDate(video.publishDate)}}</h6>
          <h4>{{video.title}}</h4>
        </a>
    </div>
</template>

<script>
import moment from 'moment'
export default {
    props: {
        video: {
            type: Object
        }
    },
    methods: {
        formatDate(date) {
            return moment(date).format("Do MMMM YYYY");
        },
    }
}
</script>

<style scoped>

div.video-row {
  padding: 1em;
}

div.video-row:hover, div.video-row:focus {
  background-color: rgba(240, 240, 240, 0.64);
}

div.video-row a{
  text-decoration: none;
  color: black;
}
div.video-row img {
  width: 100%;
}

div.video-row h6 {
  margin: 0.3rem 0;
  font-size: 0.88rem;
  font-weight: 700;
  letter-spacing: -0.01rem;
}

div.video-row h4 {
  margin: 0px;
  font-size: 1rem;
  line-height: 1.25;
  font-weight: 500;
  letter-spacing: -0.01rem;
}

</style>