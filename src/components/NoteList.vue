<template>
  <div class="note-list">
    <p>Listy List</p>
    <NoteThumbnail @updateNote="setCurrentNote" v-for="note in notes" :note="note">{{note.title}}</NoteThumbnail>
  </div>
</template>

<script>
import NoteThumbnail from './NoteThumbnail.vue'
;
export default {
  name: 'NoteList',
  props: {
    index: Number,
    notes: Array,
  },
  components: {
    NoteThumbnail
  },
  methods: {
    setCurrentNote(note) {
      this.$emit('updateNote', note)
    }
  },
  created() {
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.note-list {
  align-items: center;
  background-color: #F6F1D1;
  display: flex;
  flex-direction: column;
  padding: 1rem 3rem;
  width: 20%;
}
</style>
