<template>
  <div>
    <div v-for="book in filteredBooks" :key="book.id">
        <Book :book="book"></Book>
    </div>
    <div>
    </div>
  </div>
</template>

<script>
import Book from "../../components/Book.vue";
  export default {
  name: "App",
  components: { Book },
  data() {
    return {
    }
  },
  // computed:{
  //   filteredBooks(){
  //     return this.books.filter(book => book.title.toLowerCase().includes(this.search.toLowerCase()))
  //   }
  // }
}
</script>
