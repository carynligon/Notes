<template>
  <div @click="setNote" class="note-thumbnail">
    <div>{{note.title}}</div>
  </div>
</template>

<script>
export default {
  name: 'NoteThumbnail',
  props: {
    note: Object,
    setCurrentNote: Function,
  },
  created() {
  },
  methods: {
    setNote() {
      this.$emit('interface', this.note)
    }
  } 
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.note-thumbnail {
  background-color: #ffffff;
  border: 1px solid #ffffff;
  margin: 1rem 0;
  padding: .5rem;
  width: 95%;

  &:focus, &:hover {
    border: 1px solid #40798C;
  }
}
</style>
