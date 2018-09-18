<template>
  <div class="col-full">
    <h1>Fucked up vuckorum.</h1>
    <ThreadList :threads="threads"/>
  </div>
</template>

<script>
import sourceData from '@/data'
import ThreadList from './ThreadList'

export default {
  name: 'HelloWorld',

  components: {
    ThreadList
  },

  data () {
    return {
      threads: Object.values(sourceData.threads),
      posts: sourceData.posts,
      users: sourceData.users
    }
  }
}
</script>
