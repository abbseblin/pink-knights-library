<template>
<header>
<nav class="titelBanner container flex justify-between px-4 py-8 mx-auto">
  <div>
    <h3 class="titel text-2xl font-medium">Biblioteket.se</h3>
  </div>
  <div class="links hidden space-x-8 lg:flex">
    <a class="link" href="/">Hem</a>
    <a class="link" href="/help">Hjälp</a>
    <a class="link" href="/ourTeam">Vårat team</a>
    <a href="/shoppingCart" class="link flex justify-center">Varukorg🛒</a>
  </div>
  <div class="flex lg:hidden">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      class="w-6 h-6"
      fill="none"
      viewBox="0 0 24 24"
      stroke="currentColor"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M4 6h16M4 12h16M4 18h16"
      />
    </svg>
  </div>
</nav>
</header>
</template>

<style>
.titelBanner{
  background-color: #FFFFFF;
  border-bottom: 2px solid black;
}
.titel {
  color: white;
  padding: 5px;
  border-radius: 5px;
  background-color: #b11409c9;
}
.links{
  color: #371203;
  font-size: larger;
  font-weight: bold;
}
.link{
  background-color: #fc5c1dcc;
  padding: 5px;
  border-radius: 5px;
  text-decoration-line: underline;
    transition: transform .5s;
}
.link:hover{
  transform: scale(1.1);
}
</style>
<script>
export default {
    data() {
    return{
    open: false
    }
    },
    methods: {
        toggle(){
            this.open = !this.open;
            console.log(this.open)
        }
    }
}
</script>

