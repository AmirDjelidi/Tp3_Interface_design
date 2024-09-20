<template>
<nav>
  <div class="menu-item"><a href="#">Home</a> </div>
  <div class="menu-item"><a href="#">I'm Yu</a> </div>
  <div class="menu-item"><a href="#">He's me</a> </div>
  <div class="menu-item"><a href="#">Don't contact me</a> </div>
</nav>
  <div>
    <h1>Il n'y a pas de bonne ou de mauvaise Vue 😉</h1>
  </div>
</template>

<script>

export default {
  name: 'HomePage',
}
</script>

<style scoped>
nav {
  display: flex;
  background-color: green;
  justify-content: space-around;
}
nav a{
  color: white;
  text-decoration: none;
}

h1 {
  text-align: center;
  font-family: "Bebas Neue", sans-serif;
  font-weight: 400;
  font-style: normal;
}
</style>
