<template>
  <div
    class="home p-2"
  >
    <h1>
      {{ $t('message') }}
    </h1>
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
}
</script>
