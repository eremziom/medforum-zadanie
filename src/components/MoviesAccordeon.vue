<template>
  <div>
    <div class="accordion" id="movieAccordeon">
      <div class="accordion-item" v-for="(item, index) in this.movies" :key="index">
        <h2 class="accordion-header" :id="item.id">
          <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" :data-bs-target="'#id'+item.id" aria-expanded="true" :aria-controls="'id'+item.id" @click="loadMovie(item.id)">
            {{ item.title }}
          </button>
        </h2>
        <div :id="'id'+item.id" class="accordion-collapse collapse" :aria-labelledby="item.id" data-bs-parent="#movieAccordeon">
          <div class="accordion-body">
            <!-- Can use v-if="loadedMovie === item.id" for loading only move we need -->
            <MovieComponent :movie="item" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import data from '@/data.json'
import MovieComponent from '@/components/MovieComponent.vue'

export default {
  name: 'MoviesAccordeon',
  components: {
    MovieComponent
  },
  methods: {
    loadMovie(id){
      this.loadedMovie = id
    }
  },
  data() {
    return {
      movies: data,
      loadedMovie: null
    }
  }
}
</script>