<template src="../views/faqs.html"></template>

<script>
  import axios from 'axios'
  export default {
    data () {
      return {
        faqs: []
      }
    },
    async asyncData ({env, error}) {
      let response
      try {
        response = await axios.get(env.baseUrl + '/data/faqs.json')
      } catch (e) {
        error(e)
      }
      return {
        faqs: response.data
      }
    }
  }
</script>
