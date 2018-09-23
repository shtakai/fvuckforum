<template>
  <div class="col-full push-top">
    <h1>Create a fucked up thread in <i>{{forum.name}}</i></h1>

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
        <button class="btn btn-ghost">Cancel</button>
        <button class="btn btn-blue" type="submit" name="Publish">Publish</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  props: {
    forum: {
      required: true,
      type: Object
    }
  },

  data () {
    return {
      title: '',
      text: ''
    }
  },

  methods: {
    save () {
      this.$store.dispatch('createThread', {
        forumId: this.forum['.key'],
        title: this.title,
        text: this.text
      })
    }
  }
}
</script>

<style scoped>

</style>
