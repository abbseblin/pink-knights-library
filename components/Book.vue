<template>
  <div class="main">

    <div class="book">
      <h3>{{ book.title }}</h3>
      <p>{{book.body}}</p>
      <img :src="book.img" alt="">
    </div>
    </div>

</template>

<script>
export default {
  props: ["book"],
  data() {
        return {

        }
    }

};

</script>
<style>
.book{
  order: 0;

  display: flex;
  flex-direction: column;


  transition: transform .2s;
  margin: 50px;
  background-color: black;
  color: white;
  width: 300px;
  height: 350px;
  /* padding-left: 45px;
  padding-bottom: 10px; */
  border-radius: 10px;


  }

  /* .post:hover p {
    transform: scaleY(0.66)
  } */

  .book:hover {
    transform: scale(1.15);
    /* transform: scaleX(1.2); */
    /* transform-origin: bottom; */

  }
  .flexBook{
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
  }

  .main{
    display: flex;
    width:310px;
    background-color:red ;
    flex-direction: row;
    justify-content: space-evenly;

  }
  </style>
