<template>
  <div class="note-edit">
    {{body}}
  </div>
</template>

<script>
export default {
  name: 'EditMode',
  props: {
    note: Object,
  },
  data() {
    return {
      body: ''
    }
  },
  created() {
    console.log('edit mode created', this.note);
  },
  watch: {
    note(newNote, old) {
      console.log('note changed in edit mode', newNote, old)
      this.body = newNote.body;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
