<script>
export default {
  data() {
    return {
      message: 'Hello World',
      greetings: 'My first web vue app',
      movieInput: '',
      movieArray: [],
    }
  },

  methods: {
    addMovie() {
      this.movieArray.push(this.movieInput)
      console.log(JSON.stringify(this.movieInput))
      this.movieInput = ''
    },
    rmMovie(index) {
      this.movieArray.splice(index, 1)
    },
  },
}
</script>

<template>
  <header>
    <h1>{{ message }}</h1>
    <p>
      {{ greetings }}
    </p>
  </header>
  <div class="movie-forms">
    <input type="text" placeholder="Nome da série ou filme" v-model="movieInput" />
    <button v-on:click="addMovie">Adicionar</button>
  </div>

  <div class="movie-list">
    <h2 id="movie-list">Movie List</h2>
    <ul aria-labelledby="movie-list">
      <li v-for="(movie, index) in movieArray" :key="movie">
        {{ movie }}
        <button class="rm-movie" v-on:click="rmMovie(index)">x</button>
      </li>
    </ul>
  </div>

  <div class="movie-count">Total: {{ movieArray.length }}</div>
</template>

<style scoped>
h1 {
  color: white;
}

div.movie-forms {
  display: flex;
  gap: 10px;
}
</style>

<!--

DESAFIO

colocar um botao de remover e remover o objeto
contar os objetos

-->
