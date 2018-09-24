<template>
  <form @submit.prevent="save">
    <div class="form-group">
      <label for="thread_title">Title:</label>
      <input
        v-model="form.title"
        type="text"
        name="title"
        id="thread_title"
        class="form-input"
      />
    </div>

    <div class="form-grou">
      <label for="thread_title">Content:</label>
      <textarea
        v-model="form.text"
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
  props: {
    title: {
      type: String,
      default: ''
    },
    text: {
      type: String,
      default: ''
    }
  },

  data () {
    return {
      form: {
        title: this.title,
        text: this.text
      }
    }
  },

  methods: {
    save () {
      this.$emit('save', {title: this.form.title, text: this.form.text})
    },

    cancel () {
      this.$emit('cancel')
    }
  }
}
</script>

<style scoped>

</style>
