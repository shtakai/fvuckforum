<template>
  <div class="col-full push-top">
    <h1>Fucked up vuckorum.</h1>
    <CategoryList :categories="categories"/>
  </div>
</template>

<script>

import CategoryList from '@/components/CategoryList'

export default {
  components: {
    CategoryList
  },

  data () {
    return {
      categories: Object.values(this.$store.state.categories)
    }
  },

  beforeCreate () {
    console.log('BEFORE CREATE', this.categories)
  },
  created () {
    console.log('CREATED', this.categories)
  },
  beforeMount () {
    console.log('BEFORE MOUNT', this.categories)
  },
  mounted () {
    console.log('MOUNTED', this.categories, this.$el.innerText.length)
  },
  beforeDestroy () {
    console.log('BEFORE DESTROY: turn off listeners', this.categories)
  },
  destroyed () {
    console.log('DESTROYED', this.categories)
  }

}
</script>
