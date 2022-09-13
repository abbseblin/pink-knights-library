<template>
  <div @click="link" class="page">
    <div class="book">
      <h1>{{ book.title }}</h1>
      <h1>{{ book.author }}</h1>
    </div>
  </div>
</template>

<script>
import { traverse } from '@babel/types'

export default {
  props: ["book"],
    methods:{
    link: function(){
      window.location.href = "http://localhost:3000/books/" + this.book.id;
    },
  },

  data() {
        return {

        }
    }
};

</script>
