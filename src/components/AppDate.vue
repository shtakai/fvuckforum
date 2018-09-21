<template>
  <span :title="timestamp | humanFriendryDate">{{timestamp | diffForHuman}}</span>
</template>

<script>
import moment from 'moment'
export default {
  props: {
    timestamp: {
      required: true,
      type: Number
    }
  },
  filters: {
    humanFriendryDate (date) {
      return moment.unix(date).locale('ar-IQ').format('MMMM Do YYYY, h:mm:ss a')
    },
    diffForHuman (date) {
      return moment.unix(date).locale('ar-IQ').fromNow()
    }
  }
}
</script>

<style scoped>

</style>
