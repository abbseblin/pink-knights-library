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
      //skriv in addressen för själva hemsidan (inte databasen)
      window.location.href = "http://localhost:52139/" + this.book.id;
    },
  },

  data() {
        return {
        }
    }
};

</script>
