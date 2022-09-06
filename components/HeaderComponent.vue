<template>
<header>
<nav class="titelBanner container flex justify-between px-4 py-8 mx-auto">
  <div>
    <h3 class="titel text-2xl font-medium">Pensionärsbibblan</h3>
  </div>
  <div class="links hidden space-x-8 lg:flex">
    <a href="/">Home</a>
    <a href="/about-us">About Us</a>
    <a href="">Blogs</a>
    <a href="">Our Team</a>
    <a href="">Contact Us</a>
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

<style scoped>
.titelBanner{
  background-color: #FFFFFF;
  border-bottom: 2px solid black;
}
.titel {
  color: #371203;
}
.links{
  color: #371203;
}
</style>
