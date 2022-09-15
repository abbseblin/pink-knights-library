<template>
  <div class="idPage">
    <img class="postImage" :src="post.img" alt="NO IMAGE">
    <div class="idText">
    <h1 class="postTitle texth1">{{post.title}}</h1>
    <h1 class="postAuthor texth1">{{post.author}}</h1>
    <h1 class="postGenre texth1"><b>Genre:</b> {{post.genre[0]}}</h1>
    <h1 class="postLang texth1"><b>Språk: </b>{{post.lang}}</h1>
    <h1 class="postCopies texth1"><b>Antal böcker tillgängliga: </b>{{post.copies}} st</h1>

    <button class="shopBtn">Lägg i varukorg</button>
    </div>
  </div>
</template>

<script>
export default {
    async asyncData({ params, $axios }) {
      const post = await $axios.$get(`http://localhost:3000/books/${params.id}`)
      return { post }
    }
  }
</script>

<style scoped>
.idPage{
  display: flex;
  flex-direction: row;
  position: absolute;
  left: 80px;
  top: 160px;
  background-color: burlywood;
  width: 800px;
  padding: 20px;
  border-radius: 10px;
}
.idText{
  display: flex;
  flex-direction: column;
  margin-left: 50px;
  margin-top: 40px;
}
.postImage{
  height: 350px;
  width: 300px;
}
.postTitle{
  font-weight: bolder;
}
.texth1{
  padding: 5px;
  font-size: 23px;
}
.shopBtn{
  color: white;
  background-color: rgba(3, 150, 3, 0.864);
  width: 150px;
  height: 60px;
  border-radius: 10px;
  transition: transform .6s;
  margin-top: 20px;
  margin-left: 30px;
}
.shopBtn:hover{
  transform: scale(1.05);
}
</style>

