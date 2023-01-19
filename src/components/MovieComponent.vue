<template>
  <div>
    <video
      width="100%"
      height="auto"
      controls
      :id="'video'+movie.id"
      autoplay
      muted
      v-on:play="moviePlayCheck"
      v-on:pause="moviePaused"
      v-on:ended="consoleMessage('movie.ended')"
      v-on:timeupdate="movieTimeCheck"
      v-on:loadedmetadata="sendLength"
    >
      <source
        :src="movie.url"
        type="video/mp4">
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
  mounted() {
    let video = document.getElementById('video'+this.movie.id)
    this.video = video
  },
  methods: {
    sendLength(){
      this.videoLength = this.video.duration
      this.$emit('videoLength', this.videoLength, this.movie.id)
    },
    movieTimeCheck(){
      let halfOfVideo = this.video.duration / 2
      this.video.currentTime > halfOfVideo && !this.middleAchieved
        ? (this.consoleMessage('movie.middle'), this.changeMiddleAchieved())
        : this.middleAchieved && this.video.currentTime < halfOfVideo
        ? this.changeMiddleAchieved()
        : ''
    },
    moviePlayCheck(){
      !this.videoPaused
        ? this.consoleMessage('movie.started')
        : ''
      this.video.currentTime < 0.01 && this.videoPaused
        ? this.consoleMessage('movie.started')
        : ''
    },
    changeMiddleAchieved(){
      this.middleAchieved = !this.middleAchieved
    },
    consoleMessage(message){
      console.log(this.$t(message, {title: this.movie.title}))
    },
    moviePaused(){
      this.videoPaused = true
    },
  },
  data(){
    return {
      video: null,
      middleAchieved: false,
      videoPaused: false,
      videoLength: 0
    }
  }
}
</script>