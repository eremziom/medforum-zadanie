<template>
  <div
    class="p-2"
  >
    <h2>
      {{ $t('home.title') }}
    </h2>
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
