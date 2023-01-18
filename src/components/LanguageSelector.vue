<template>
  <div>
    <div class="btn-group" role="group">
        <button v-for="item in $i18n.availableLocales"
          :key="item"
          type="button"
          class="m-1 btn-sm"
          :class="{
            'btn btn-dark' : item !== computedLanguage,
            'btn btn-success' : item === computedLanguage
          }"
          @click="changeLanguage(item)"
        >
          {{  item.toLocaleUpperCase() }}
        </button>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'LanguageSelector', 
    computed: {
      computedLanguage() {
        return this.$i18n.locale
      }
    },
    methods: {
      changeLanguage(language){
        this.$i18n.locale = language
      }
    },
    data() {
      return {
      }
    }
  }
</script>

