<template>
  <form @submit.prevent="save">
    <div class="form-group">
      <label for="thread_title">Title:</label>
      <input
        v-model="title"
        type="text"
        name="title"
        id="thread_title"
        class="form-input"
      />
    </div>

    <div class="form-grou">
      <label for="thread_title">Content:</label>
      <textarea
        v-model="text"
        name="content"
        id="thread_content"
        row="8"
        cols="148"
        class="form-input"
      />
    </div>

    <div class="btn-group">
      <button @click.prevent="cancel" class="btn btn-ghost">Cancel</button>
      <button class="btn btn-blue" type="submit" name="Publish">Publish</button>
    </div>
  </form>
</template>

<script>
export default {
  data () {
    return {
      title: '',
      text: ''
    }
  },

  methods: {
    save () {
      this.$emit('save', {title: this.title, text: this.text})
    },

    cancel () {
      this.$emit('cancel')
    }
  }
}
</script>

<style scoped>

</style>
