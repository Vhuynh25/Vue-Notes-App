<template>
  <note_book/>
</template>

<script>
import note_book from './components/NoteBook.vue'

export default {
  name: 'App',
  components: {
    note_book
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
