<template>
  <div
    id="app" 
    class=""
  >
    <TopBar />
    <div 
      class="views-container"
    >
      <router-view/>
    </div>
    <FooterBar />
  </div>
</template>

<script>
import TopBar from '@/components/TopBar.vue'
import FooterBar from '@/components/FooterBar.vue'
  export default {
    name: 'App',
    components: {
      TopBar,
      FooterBar
    }
  }
</script>

<style lang="sass">

</style>
