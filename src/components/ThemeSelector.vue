<template>
  <div>
    <div class="btn-group flex-column flex-sm-row" role="group">
      <button v-for="item in themes"
        :key="item"
        type="button"
        class="m-1 btn-sm"
        :class="{
          'btn btn-dark' : item !== computedTheme,
          'btn btn btn-success' : item === computedTheme
        }"
        @click="changeTheme(item)"
      >
      <i 
        :class="item === 'light' ? 'bi bi-sun' : 'bi bi-moon'"></i>
      </button>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'ThemeSelector',
    computed: {
      computedTheme() {
        return this.currentTheme
      }
    },
    methods: {
      changeTheme(theme){
        document.body.classList.add(theme)
        for(let item of this.themes){
          console.log(item, theme)
          item === theme ? this.currentTheme = theme : document.body.classList.remove(item)
        }
      }
    },
    data() {
      return {
        themes: [
          'dark',
          'light'
        ],
        currentTheme: 'light'
      }
    }
  }
</script>