<template>
  <div class="col-large push-top">
    <h1>
      {{thread.title}}
      <router-link
        :to="{name: 'ThreadEdit', id: this.id}"
        class="btn-green btn-small"
        tag="button"
      >
        Edit thread
      </router-link>
    </h1>
    <p>
      By <a href="#" class="link-unstyled">{{user.name}}</a>, <AppDate :timestamp="thread.publishedAt"/>.
      <span style="float:right; margin-top: 2px;" class="hide-mobile text-faded text-small">{{repliesCount}} replies by {{contributorsCount}} contributors</span>
    </p>
    <PostList :posts="posts"/>
    <PostEditor
      :threadId="id"
    />
  </div>
</template>

<script>
  import PostList from '@/components/PostList'
  import PostEditor from '@/components/PostEditor'

  export default {
    components: {
      PostList,
      PostEditor
    },

    props: {
      id: {
        required: true,
        type: String
      }
    },

    computed: {
      thread () {
        return this.$store.state.threads[this.id]
      },

      user () {
        return this.$store.state.users[this.thread.userId]
      },

      repliesCount () {
        return this.$store.getters.threadRepliesCount(this.thread['.key'])
      },

      contributorsCount () {
        const replies = Object.keys(this.thread.posts)
          .filter(postId => postId !== this.thread.firstPostId)
          .map(postId => this.$store.state.posts[postId])
        const userIds = replies.map(post => post.userId)
        return userIds.filter((item, index) => index === userIds.indexOf(item)).length
      },

      posts () {
        const postIds = Object.values(this.thread.posts)
        return Object.values(this.$store.state.posts)
          .filter(post => postIds.includes(post['.key']))
      }
    }
  }
</script>
