<!-- *Milestone 0:
Progettare la struttura del global state sulla linea degli esercizi svolti nei giorni precedenti. -->

<!-- *Milestone 1:
Creare un layout base con una searchbar (una input e un button) in cui possiamo scrivere completamente o parzialmente il nome di un film. Possiamo, cliccando il bottone, cercare sull’API tutti i film che contengono ciò che ha scritto l’utente. Vogliamo dopo la risposta dell’API visualizzare a schermo i seguenti valori per ogni film trovato:
1. Titolo
2. Titolo Originale
3. Lingua
4. Voto -->

<script>
import { store } from './store';
import axios from 'axios';
import SearchBar from './components/SearchBar.vue'
import AppMain from "./components/AppMain.vue";

export default {
  components: {
    SearchBar,
    AppMain
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    search: function () {

      axios
      .get("https://api.themoviedb.org/3/search/movie?api_key=22bb06029ddd3823a614fa4551416767", {params: {query: this.store.query}})
      .then((resp) => {
        this.store.moviesArray = resp.data.results
        console.log(this.store.query);
        console.log(this.store.moviesArray);
      });

      axios
      .get("https://api.themoviedb.org/3/search/tv?api_key=22bb06029ddd3823a614fa4551416767", {params: {query: this.store.query}})
      .then((resp) => {
        this.store.TvArray = resp.data.results
        console.log(this.store.moviesArray);
      })

    }
  }
}
</script>

<template>
<SearchBar @filter="search"/>
<AppMain />
</template>

<style lang="scss">

</style>