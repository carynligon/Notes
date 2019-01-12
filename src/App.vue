<template>
  <div id="app">
    <NoteWindow :notes="notes" />
  </div>
</template>

<script>
import NoteWindow from './components/NoteWindow.vue';

import notes from './fixtures/notes.json';

export default {
  name: 'app',
  components: {
    NoteWindow,
  },
  data: () => ({
    notes,
  })
};
</script>

<style lang="scss">
body {
  margin: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
