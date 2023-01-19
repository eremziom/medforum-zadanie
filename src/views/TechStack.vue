<template>
  <div 
    class="p-2"
  >
    <h2>
      {{ $t('tech.title') }}
    </h2>
    <div
      class="tech"
    >
      <ul class="list-group">
        <li class="list-group-item" v-for="(item, index) in tech" :key="index">{{ item }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import tech from '@/tech.json'
export default {
  name: 'TechStack',
  data() {
    return {
      tech: tech
    }
  }
}
</script>
