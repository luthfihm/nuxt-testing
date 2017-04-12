<template src="../views/items.html"></template>
<style src="assets/css/items.css"></style>
<script>
  export default {
    data () {
      return {
        items: []
      }
    },
    beforeRouteEnter (to, from, next) {
      next(vm => {
        for (let $i = 1; $i <= 10; $i++) {
          vm.items.push({
            name: makeid(10),
            description: makeid(100)
          })
        }
      })
    },
    methods: {
      fetchData () {
        for (let $i = 1; $i <= 1000; $i++) {
          this.items.push({
            name: makeid(10),
            description: makeid(100)
          })
        }
      }
    }
  }
  function makeid (char) {
    let text = ''
    const possible = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789'
    char = (char === undefined) ? 5 : char
    for (let i = 0; i < char; i++) {
      text += possible.charAt(Math.floor(Math.random() * possible.length))
    }
    return text
  }
</script>
