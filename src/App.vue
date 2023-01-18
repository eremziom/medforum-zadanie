
import LanguageSelector from './components/LanguageSelector.vue';

<template>
  <div id="app">
    <div class="d-flex justify-content-between align-items-center">
      <ThemeSelector />
      <nav>
        <router-link to="/">{{ $t('router.home') }}</router-link> |
        <router-link to="/about">{{ $t('router.about_me') }}</router-link>
      </nav>
      <LanguageSelector />
    </div>
    <router-view/>
  </div>
</template>

<script>
import LanguageSelector from '@/components/LanguageSelector.vue'
import ThemeSelector from '@/components/ThemeSelector.vue'
  export default {
    name: 'App',
    components: {
      LanguageSelector,
      ThemeSelector
    }
  }
</script>

<style lang="sass">

</style>
