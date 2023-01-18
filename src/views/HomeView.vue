<template>
  <div class="home">
    {{ $t('message') }}
    <button @click="changeLang">change lang</button>
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
