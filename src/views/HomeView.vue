<template>
  <div class="home">
    <h1>{{ $t('message') }}</h1>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'HomeView',
  components: {
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
