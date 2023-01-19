<template>
  <div>
    <video width="640" height="480" controls :id="'video'+movie.id" autoplay muted v-on:play="movieStart" v-on:pause="moviePaused" v-on:ended="movieEnded" v-on:timeupdate="movieTimeCheck">
      <source :src="movie.url" type="video/mp4">
      Your browser does not support the video tag.
    </video>
  </div>
</template>

<script>
export default {
  name: 'MovieComoponent',
  props: {
    movie: Object,
  },
  methods: {
    changeMiddleAchieved(){
      this.middleAchieved = !this.middleAchieved
    },
    movieTimeCheck(){
      let video = document.getElementById('video'+this.movie.id)
      let halfOfVideo = video.duration / 2
      video.currentTime > halfOfVideo && !this.middleAchieved
        ? (this.movieMiddle(), this.changeMiddleAchieved())
        : this.middleAchieved && video.currentTime < halfOfVideo
        ? this.changeMiddleAchieved()
        : ''
    },
    movieEnded(){
      console.log(this.$t('movie.ended'))
    },
    movieStart(){
      !this.videoPaused ?
      console.log(this.$t('movie.started'))
      : ''
    },
    movieMiddle(){
      console.log(this.$t('movie.middle'))
    },
    moviePaused(){
      this.videoPaused = true
    },
  },
  data(){
    return {
      middleAchieved: false,
      videoPaused: false,
    }
  }
}
</script>