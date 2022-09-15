<template>
  <div>
    {{bla.books[1].author}}
  </div>
</template>

<script>
export default {
    async asyncData({ params, $axios }) {
      const post = await $axios.$get(`https://api.nuxtjs.dev/posts/1}`)
      console.log(params.id);
      const bla = require("../db.json");
      return { bla, params }
    }
  }
</script>


