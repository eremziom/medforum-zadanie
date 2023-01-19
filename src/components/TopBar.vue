<template>
  <div 
    class="top-container"
  >
    <div 
      class="d-flex justify-content-between align-items-center"
    >
      <ThemeSelector />
      <nav>
        <router-link 
          to="/"
        >
          {{ $t('router.home') }}
        </router-link> |
        <router-link
          to="/tech-stack"
        >
          {{ $t('router.tech_stack') }}
        </router-link>
      </nav>
      <LanguageSelector />
    </div>
  </div>
</template>

<script>
import LanguageSelector from '@/components/LanguageSelector.vue'
import ThemeSelector from '@/components/ThemeSelector.vue'
  export default {
    name: 'TopBar',
    components: {
      LanguageSelector,
      ThemeSelector
    }
  }
</script>

<style lang="sass">

</style>