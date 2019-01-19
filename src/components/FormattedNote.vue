<template>
  <div class="note-formatted">
    Formatted!
    <div v-html="body"></div>
  </div>
</template>

<script>
import showdown from 'showdown';

export default {
  name: 'FormattedNote',
  props: {
    note: Object,
  },
  data() {
    return {
      converter: new showdown.Converter(),
      body: ''
    }
  },
  created() {
  },
  watch: {
    note(newNote, old) {
      console.log('note changed in edit mode', this)
      this.body = this.converter.makeHtml(newNote.unformatted_body);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
