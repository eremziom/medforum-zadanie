<template>
  <div class="home">
    <h1>{{ $t('message') }}</h1>
    <MoviesAccordeon />
  </div>
</template>

<script>
import MoviesAccordeon from '@/components/MoviesAccordeon.vue'

export default {
  name: 'HomeView',
  components: {
    MoviesAccordeon
  },
  mounted() {
    console.log(this.$i18n)
  },
  methods: {
    changeLang(){
      console.log(this.$i18n.locale)
      this.$i18n.locale = 'en'
    }
  }
}
</script>
