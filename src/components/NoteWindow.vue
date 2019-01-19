<template>
  <div class="note-window">
    <NoteList @updateNote="setCurrentNote" :notes="notes" />
    <EditMode :note="currentNote" />
    <FormattedNote :note="currentNote" />
  </div>
</template>

<script>
import EditMode from './EditMode.vue';
import FormattedNote from './FormattedNote.vue';
import NoteList from './NoteList.vue';

export default {
  name: 'NoteWindow',
  props: {
    msg: String,
    notes: Array,
  },
  data: function () {
    return {
      currentNote: {}
    }
  },
  components: {
    EditMode,
    FormattedNote,
    NoteList,
  },
  methods: {
    setCurrentNote(note) {
      this.currentNote = note;
    },
  },
  watch: {
    currentNote(newNote, old) {
      console.log('note changed', newNote, old)
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.note-window {
  background: #F6F9F4;
  display: flex;
  height: 100vh;
  width: 100%;
}
</style>
